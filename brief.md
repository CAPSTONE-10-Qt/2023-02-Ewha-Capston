#### ������Ʈ��

GPU�� ������ ����� �Ŵ� ��� �� (LLM) �߷� ȿ���� ��� �� ����ȭ
#### �ۼ���

2023��10��08��
#### ����ȣ �� ����

01. Optimus GPrime
#### ������������
���Һд�

Ȳ����(2176427) ����,	���� ���� ���� �м�, �������ϸ�			
������(2173109) ����,	���� ���� ���� �м�, ��׶��� ��ġ			
���̰�(2276327) ����,	���� ���� ���� �м�, ���̺귯�� �� �����ӿ�ũ ���� 			
#### ����������

���� ������
#### ����Ҽ�ȸ��

ETRI
#### ���伺��, ����

���� ������
#### ���������� ����ġ 
����

�Ŵ� ��� �� (Large Language Model, ���� LLM)�� ���䰡 �����Կ� ���� �߷� ����� ���Ҵ� ���� �߿������� �ִ�. LLM�� �߷��� ���ؼ��� �ٷ��� GPU�� ���Ǵµ�, GPU�� ������ ����� LLM ����ȭ ����� �θ� �˷����� �ʾҴ�. ���� �� �������� GPU�� ������ ����� LLM ����ȭ ����� �����Ͽ� LLM�� �߷��� �����ϰ�, �̿� ���Ҿ� ������ ������ ������ �Ҹ� �������� �⿩�ϰ��� �Ѵ�.
#### ������ ����

ChatGPT[1]�� ���� LLM�� ����� ���� �����ϰ� �ִ�. LLM�� ���� ���� ����ġ�� ����Կ� ���� �� �ð��� ������ �䱸�ϸ�, �̷��� ������ ������ ó���ϱ� ���� �ٷ��� GPU�� �ʿ�� �Ѵ�. �̷��� GPU ������ ��Ƶ� ������ ���Ϳ����� LLM ���䰡 �����Կ� ���� ���� ���� �������� �Ҹ��ϰ� �ִ�[12]. ���� GPU�� LLM �߷п� ����ȭ�Ͽ� �߷� ����� ���ҽ�Ŵ���ν�, GPU�� ������ �Ҹ� ���ҽ�Ű�� ���� �ſ� �߿��� ������ ��εǰ� �ִ�. 
#### ���ÿ���/����/
�ý��������� 
�� �Ѱ���

[���� ����]
NVIDIA���� LLM�� �߷��� ����ȭ�ϱ� ���� ���̺귯���� FasterTransformer[5]�� �����ߴ�. FasterTransformer�� �پ��� ���� ����� �����ϴµ�, KV Cache�� ȿ������ ����� ���� memory reservation�� ��ǥ���� ���� �� �� �ִ�. ������ LLM �߷� ����������, �ϳ��� ��ū�� ������ ������ �ش��ϴ� KV Cache ������ �Ҵ��ϴ� ����� ����ߴ�. ������, FasterTransformer�� ���� ������ ��ū�� ���� �޸� ������ �̸� reservation �����ν�, ������ on-demand ����� memory allocation���� �߻��� overhead�� ���ҽ�Ų��.

[�Ѱ���] 
���� ���� memory reservation ����� �ַ� LLM�� ������ �� �ִ� �ִ� ��ū ������ ����ϴ� �޸� ������ �̸� reservation �Ѵ�. ����, ��쿡 ���� ���ʿ��� �޸� �������� reservation�� �Ͽ� ����� ���� �޸� ���� �ʷ��� �� �ִٴ� �������� �ִ�[3]. ����, �޸��� ��뷮�� GPU�� �� ���� ó���� �� �ִ� request�� ���� �����ϴ� ��� �� �ϳ��̹Ƿ�, �޸� ����� �ᱹ throughput ������ ������ �̾��� �� �ִ�.
#### ���ȳ���

LLM�� KV Cache�� �޸� ����� LLM ������ �������� �ۿ��� �� �ִ�. ����, KV Cache�� ȿ�������� ��������ν� GPU�� LLM �߷��� ����ȭ �� ����� �����ϰ��� �Ѵ�.
#### �������

�����ӿ�ũ�� PyTorch[6]�� �����Ͽ� LLM �߷� ������ ���� ����ȭ ����� �����Ѵ�.
���� �򰡸� ���� NVIDIA���� �����ϴ� Nsight Systems[9]�� Nsight Compute[10] �������ϸ� ���� Ȱ���Ѵ�. 
NVIDIA GeForce RTX 3090 ���� 2�븦 ���� ȯ������ ����Ͽ�, LLM�� ������ ���Ѵ�. 
#### ����� ���α��

��� ���: CUDA, python, C++
�����ӿ�ũ: PyTorch[6]
���¼ҽ� ���̺귯��: cuBLAS[7], Huggingface Transformers[8], FasterTransformer[5]
#### ���ȿ�� �� ����

KV Cache�� ����ȭ�� ���� ������ GPU�� �޸� ������ ȿ�������� Ȱ�������ν�, ���� �ð� �ȿ� �� ���� request�� ó���� �� �ִ�. �̷ν� throughput�� �����Ͽ�, LLM�� �߷� ������ ����ų �� �ִ�. 

���Ҿ� LLM�� �������� ����� ������ ���� ���� GPU ��뷮�� �ް��� �����Կ� ����, ������ ������ ���� �Ҹ� �ɰ��� ������ �ָ�ް� �ִ�. �Ӹ� �ƴ϶� ������ ������ �µ� ������ ���� ���Ǵ� �ð��� �Ҹ� ���� �߿��� �̽��� �ٷ������. �� ������ ���� LLM�� throughput�� ������Ŵ���ν� �̿� ���� ������ ������ ���� �� �ð��� �Ҹ� ���� �ذῡ �⿩�� �� ���� ������ ���ȴ�.

�̷��� ���ȿ���� ���� �� ������ ȿ������ GPU �ڿ� Ȱ��� ���� ������ ��� ������ �⿩�ϸ�, LLM�� Ȱ���� �پ��� ���� �о߿����� ���� ��󿡵� �������� ������ ��ĥ ������ ���δ�.
#### 9�� ��ô����

LLM���� ����ϴ� Transformer[1] �� ������ ���� �������� ������ �����Ͽ���. 
Transformer�� Ȱ���� inference (�߷�) ������ attention �������� �̷���� �ִ�. attention ������ Query * Key ���� ���� attention score�� Value�� �������ν�, Query�� �ش��ϴ� �ܾ �ٸ� �ܾ�鿡 �ָ��� Ȯ���� ���ϴ� ���̴�. chatGPT�� ���� ����� ��, �츮�� prompt�� ������ �Է��Ͽ� request�� �ָ�, GPT model�� �ش� ������ query�� ����Ͽ� �ܾ�� ���� attention score�� ����� �� ���� �ܾ �����Ѵ�. ������ �ܾ�� �ٽ� Query�� ���ǰ�, �̷��� attention ������ �ݺ������ν� request�� ���� output ������ �����Ѵ�. 
#### 10�� ��ô����

LLM �� �ϳ��� LLaMA 7B[4]�� Nsight Systems[9] �� Compute[10]�� ���� �������ϸ� �Ͽ� Transformer�� ���� ������ �ľ��ϰ�, ������ �Ǵ� �κ��� Ȯ���Ͽ���. 
KV Cache��, ����ġ�� ���ؼ� ���� Key, Value ���� �����صΰ� Query�� �־��� �� �ٽ� ����� ���� �ʰ� ����� ĳ�ð��� ����ϴ� ������ ���� �߷��� ���� ��ȵ� ����̴�. ������, �̴� GPU �޸𸮿��� ���� ������ �����ϱ� ������ batch size�� �����ϰ� �Ǿ� throughput�� ���븦 �����Ѵ�. �̴� throughput ����� ���� latency �� ���̴� GPU ������ �������� ���� ���ɼ��� �ִ�.  ���� 10������ KV Cache�� batch size�� throughput�� ���ҿ� ������ ��ġ���� ������ ���� ������ �����̴�.
#### 11�� ��ô����

KV Cache�� LLM ������ ������ �Ǵ� ���� Ȯ�εǸ�, KV Cache�� ȿ������ �޸� ��� ����� ���� ���� ������ �м��Ͽ�, GPU ������ ������ KV Cache Ȱ�� ����� ������ �����̴�. 
#### 12��1�� ���� 
�ó�����

NVIDIA������ Unified Memory ����� �����ϴµ�, Unified Memory�� CPU�� GPU �� ��ġ ��� �ϳ��� �޸� �ּ� ������ ����ϴ� ���� �ǹ��Ѵ�[11]. �̸� ���� GPU ���꿡���� CPU �޸� ������ Ȱ���� �� �ִ�. ����, LLM�� �߷п� Unified Memory ����� ����� ���, KV Cache�� ���忡 Ȱ���� �� �ִ� �޸� ������ �����Ͽ� throughput ���� ����ų �� ���� ���̶� ������ ����� �̸� �����ϰ��� �Ѵ�. 
#### ��Ÿ

[References]
[1] Vaswani, A., Shazeer, N., Parmar, N., Uszkoreit, J., Jones, L., Gomez, A. N., ... & Polosukhin, I. (2017). Attention is all you need. Advances in neural information processing systems, 30.
[2] Brown, T., Mann, B., Ryder, N., Subbiah, M., Kaplan, J. D., Dhariwal, P., ... & Amodei, D. (2020). Language models are few-shot learners. Advances in neural information processing systems, 33, 1877-1901.
[3] Yu, G. I., Jeong, J. S., Kim, G. W., Kim, S., & Chun, B. G. (2022). Orca: A distributed serving system for {Transformer-Based} generative models. In 16th USENIX Symposium on Operating Systems Design and Implementation (OSDI 22) (pp. 521-538).
[4] Touvron, H., Lavril, T., Izacard, G., Martinet, X., Lachaux, M. A., Lacroix, T., ... & Lample, G. (2023). Llama: Open and efficient foundation language models. arXiv preprint arXiv:2302.13971.
[5] https://github.com/NVIDIA/FasterTransformer
[6] https://github.com/pytorch/pytorch
[7] https://developer.nvidia.com/cublas
[8] https://github.com/huggingface/transformers
[9] https://developer.nvidia.com/nsight-systems
[10] https://developer.nvidia.com/nsight-compute
[11] https://docs.nvidia.com/cuda/cuda-c-programming-guide/
[12] https://cse.engin.umich.edu/stories/power-hungry-ai-researchers-evaluate-energy-consumption-across-models
