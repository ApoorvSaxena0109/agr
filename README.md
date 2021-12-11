Using already trained model. 

Runing
python run_classifier.py 
--task_name=cola 
--do_train=true 
--do_eval=true 
--do_predict=true 
--data_dir=./data/ 
--vocab_file=./cased_L-12_H-768_A-12/vocab.txt 
--bert_config_file=./cased_L-12_H-768_A-12/bert_config.json 
--init_checkpoint=./cased_L-12_H-768_A-12/bert_model.ckpt 
--max_seq_length=128 
--train_batch_size=32 
--learning_rate=2e-5 
--num_train_epochs=3.0 
--output_dir=./bert_output/ 
--do_lower_case=False

export TRAINED_MODEL_CKPT=./bert_output/model.ckpt

python run_classifier.py 
--task_name=cola 
--do_predict=true 
--data_dir=./data 
--vocab_file=./cased_L-12_H-768_A-12/vocab.txt 
--bert_config_file=/cased_L-12_H-768_A-12/bert_config.json 
--init_checkpoint=$TRAINED_MODEL_CKPT
--max_seq_length=128 
--output_dir=./bert_output

test_result.tsv
