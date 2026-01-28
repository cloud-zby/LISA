```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
wget https://github.com/Dao-AILab/flash-attention/releases/download/v2.8.3/flash_attn-2.8.3+cu12torch2.8cxx11abiTRUE-cp310-cp310-linux_x86_64.whl
pip install ./flash_attn-2.8.3+cu12torch2.8cxx11abiTRUE-cp310-cp310-linux_x86_64.whl
pip install modelscope
modelscope download --model AI-ModelScope/LISA-7B-v1-explanatory --local_dir ./LISA-7B-v1-explanatory
CUDA_VISIBLE_DEVICES=0 python chat.py --version='./LISA-7B-v1-explanatory' --precision='fp16' --load_in_4bit


```