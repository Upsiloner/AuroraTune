# AuroraTune

### ?? ��Ŀ��������Դ����

#### 1. ��������
Ϊ�˼��� Docker �������ȡ�ٶȣ�������ʹ�ù��ڵľ���Դ�����磬������ʹ�ð����ơ�DaoCloud�����׵��ṩ�ľ������

�� Linux ϵͳ�ϣ�ִ���������
```bash
sudo mkdir -p /etc/docker
sudo vim /etc/docker/daemon.json
```
������������ӵ� daemon.json �У�
```bash
{
  "registry-mirrors": [
    "https://mirror.baidubce.com",
    "https://docker.mirrors.ustc.edu.cn",
    "https://hub-mirror.c.163.com"
  ]
}
```
�� Windows ϵͳ�ϣ�������ͨ�� Docker Desktop UI ���ü�������ѡ�� Settings > Docker Engine��Ȼ������������Ӿ���Դ��

������� Docker ������ʹ������Ч��
```bash
sudo systemctl restart docker
```

#### 2. �������з���
����Ŀ��Ŀ¼�£�ʹ�������������� Docker ������
```bash
docker compose up --build
```

#### 3. ʧ��ʱ��ε�����ȡ����

����ڹ�������������ʧ�ܣ�������ϣ��������ȡ���񣬿��Ե�����ȡ���������»��޸�����
```bash
docker pull your-image
```
��ĳЩ����£����ܻ���Ҫɾ�����ػ���ľ����������ȡ��
```bash
docker rmi <image_id>  # ɾ�����ؾ���
docker-compose up --build  # ���¹�������������
```