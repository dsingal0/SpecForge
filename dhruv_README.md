Done. I've added support for loading HuggingFace datasets with non-train splits:
Changes made:
1. Added --hf-data-path argument (was missing but referenced in code)
2. Removed duplicate --hf-split argument definition
3. Added --output-path argument (was referenced but not defined)
4. Added "messages" dataset type with process_messages_row function to handle system/user/assistant roles
5. Added logic to handle "messages" dataset in main function
Usage:
python scripts/prepare_data.py --dataset messages --hf-data-path nvidia/Nemotron-Instruction-Following-Chat-v1 --hf-split chat_if
Or use --dataset hf for raw data without processing:
python scripts/prepare_data.py --dataset hf --hf-data-path nvidia/Nemotron-Instruction-Following-Chat-v1 --hf-split chat_if

Done. Now you can use --dataset messages with local files:
For local .jsonl files:
python scripts/prepare_data.py --dataset messages --data-path /path/to/your/data.jsonl
For HuggingFace datasets:
python scripts/prepare_data.py --dataset messages --hf-data-path nvidia/Nemotron-Instruction-Following-Chat-v1 --hf-split chat_if
