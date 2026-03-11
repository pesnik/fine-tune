train:
	mlx_lm.lora \
	  --model ~/Models/MLX-Models/Qwen3.5-0.8B \
	  --train \
	  --batch-size 1 \
	  --num-layers 4 \
	  --data data

retrain:
	mlx_lm.lora \
	  --model ~/Models/Qwen/Qwen3.5-0.8B \
	  --train \
	  --data data \
	  --num-layers 8 \
	  --batch-size 2 \
	  --iters 5000 \
	  --learning-rate 1e-5 \
	  --grad-checkpoint \
	  --resume-adapter-file ./adapters/adapters.safetensors

test:
	mlx_lm.generate \
	  --model ~/Models/Qwen/Qwen3.5-0.8B \
	  --adapter-path ./adapters \
	  --max-tokens 50 \
	  --prompt "table: 1-10015132-16 
	columns: Player, No., Nationality, Position, Years in Toronto, School/Club Team
	Q: What is terrence ross' nationality
	A: SELECT"

fuse:
	mlx_lm.fuse \
	  --model ~/Models/Qwen/Qwen3.5-0.8B \
	  --adapter-path ./adapters \
	  --save-path ~/Models/Qwen/Qwen3.5-0.8B-wikisql
