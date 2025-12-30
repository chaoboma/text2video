https://huggingface.co/DFloat11/Wan2.2-T2V-A14B-2-DF11

modelscope download Wan-AI/Wan2.2-T2V-A14B-Diffusers --local_dir ./Wan-AI/Wan2.2-T2V-A14B-Diffusers 
modelscope download DFloat11/Wan2.2-T2V-A14B-2-DF11 --local_dir ./DFloat11/Wan2.2-T2V-A14B-2-DF11
modelscope download DFloat11/Wan2.2-T2V-A14B-DF11 --local_dir ./DFloat11/Wan2.2-T2V-A14B-DF11
pip install -U dfloat11[cuda12] 

CUDA_VISIBLE_DEVICES=1 PYTORCH_ALLOC_CONF=expandable_segments:True python t2v_dfloat11.py --cpu_offload --prompt "a small boy running in a park,smiling" -output "boy.mp4"
