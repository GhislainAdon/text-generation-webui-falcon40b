cd /text-generation-webui
git clone https://github.com/Honkware/text-generation-webui.git
pip install -r requirements.txt
 
git clone https://github.com/PanQiWei/AutoGPTQ
cd AutoGPTQ
pip install . # This step requires CUDA toolkit installed
 
 
cd /text-generation-webui
 
 
python server.py --share --chat --auto-devices --model llama --autogptq --trust-remote-code
 
 
Edit text-generation-webui/modules/AutoGPTQ_loader.py add a new line after line 37:
'trust_remote_code': shared.args.trust_remote_code,

Lien vers le s models 
https://huggingface.co/tiiuae/falcon-40b

https://huggingface.co/TheBloke/falcon-40b-instruct-GPTQ

https://www.youtube.com/watch?v=21mHov4Whag
