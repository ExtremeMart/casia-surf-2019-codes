

1����������ݼ����
    1.1 ��ȡ���ݼ�����CASIA-SURF�ļ��У��������phase1��phase2�����ļ��У�����phase1����ѹtrain.zip��valid.zip�ļ���
	�õ�Training�ļ��У�train_list.txt�ļ���Val�ļ��С�val_public_list.txt�ļ���
    1.2 ������Ŀ�����ļ���casia-surf-2019-codes������CASIA-SURFĿ¼���棬��֤��phase1ͬĿ¼��

2��������װ(ubuntu 16.04):
    2.1 �������նˣ�cd��casia-surf-2019-codesĿ¼��ִ�У� pip install -r requirements.txt

3�����ݼ�Ԥ����
    3.1 �������ն�,cd��casia-surf-2019-codesĿ¼������ִ�У�
	3.1.1 python data_preprocess.py  ������val���ݼ���list�ļ���
	3.1.2 python data_preprocess.py --train ������train���ݼ���list��
	3.1.3 cd data
	3.1.4 python im2rec.py train_depth_all_112_29266.lst ../../phase1 ������train���ݼ���.rec�ļ�������mxnetѵ����
	3.1.5 python im2rec.py val_depth_all_112_9608.lst ../../phase1 ������val���ݼ���.rec�ļ�������mxnet��֤��

4��ģ��ѵ��
    4.1 �������նˣ�cd��casia-surf-2019-codesĿ¼��ִ�У� python train_depth_shufflenet_v2.py
	ע��1) ����ʹ�õ��ǰ���4��GPU�ķ�����������Ϊ��11G Memory, GeForce GTX 1080��
	    ���������ã�CPU��Intel(R) Core(TM) i7-6850K CPU @ 3.60GHz 12�ˣ�64G�ڴ棬1TB��̬Ӳ�̣�
	    2) ѵ������ʹ����1,2,3��GPU����ѵ����batch_size=2048��
	
5������
    5.1 �������նˣ�cd��casia-surf-2019-codesĿ¼��ִ�У� python commit.py ../phase1/val_public_list.txt --load-epoch 554
	ע������ִ����󣬻��ڵ�ǰĿ¼������ commit_depth_%Y-%m-%d.txt ��ʽ�Ľ���ļ�
	    commit.py ��һ������Ϊ���ύ�ɼ���list�ļ����ڶ�������load-epoch��ʾ�����ص�load-epoch����ģ�ͽ���Ԥ�⡣