# 少样本X光图片违禁物检测系统
对X光图片进行指定种类违禁物检测的平台，涉及CLIP模型的微调和推理过程。
## 少样本X光图片违禁物检测 - 安全检测平台使用指南

---

在主机安装docker并正确配置后，在主机终端依次运行以下命令：

### 1. 拉取镜像
```
docker pull registry.cn-shanghai.aliyuncs.com/suvanka/comp2023:v1
```

### 2. 创建容器
```
docker run -itd --privileged=true --name anomaly-detection -p 17689:80 -p 8000:8000 registry.cn-shanghai.aliyuncs.com/suvanka/comp2023:v1
```

$\color{red}{如果是重启容器，请执行：}$
```
docker restart anomaly-detection
```

### 3. 打开终端
```
docker exec -it anomaly-detection /bin/bash
```

### 4. 进入目录
```
cd /AnomalyDetection/HelloWorld
```

### 5. 启动服务
```
nohup python3.6 manage.py runserver > /home/log  2>&1 &
```

### 6. 进入目录
```
cd ../generator
```

### 7. 在本机浏览器打开网址：**http://127.0.0.1:17689/**

用户名和密码均输入**admin**登录

### 8. 回到控制台，运行下列命令，产生实时数据
```
python3.6 generator.py
```

然后在浏览器中可观察到检测结果，并进行各种操作

---

### 备注

- 请确保主机有至少6.5GB的硬盘空间
- 用户admin为管理员，如果需要测试安检员的受限用户，用户名和密码均输入dwq登录
- 如在下载镜像时遇到网络问题，请在主机设置可用的网络代理
