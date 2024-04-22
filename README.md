环境配置
conda create -n llama3 python=3.10
conda activate llama3
conda install pytorch==2.1.2 torchvision==0.16.2 torchaudio==2.1.2 pytorch-cuda=12.1 -c pytorch -c nvidia

下载模型
安装git-lfs
conda install git
conda install git-lfs
下载模型
cd autodl-tmp
mkdir -p model
cd model
git clone https://code.openxlab.org.cn/MrCat/Llama-3-8B-Instruct.git Meta-Llama-3-8B-Instruct

下载web
git clone https://github.com/SmartFlowAI/Llama3-XTuner-CN
下载xtuner
git clone -b v0.1.18 https://github.com/InternLM/XTuner
cd XTuner
pip install -e .

运行web
streamlit run /root/autodl-tmp/Llama3-XTuner-CN/tools/internstudio_web_demo.py   /root/autodl-tmp/model/Meta-Llama-3-8B-Instruct --server.port 6006 --server.address 127.0.0.1
需要设置映射
ssh -CNgv -L 6006:127.0.0.1:6006 root@connect.自己的.com -p 自己的端口号
