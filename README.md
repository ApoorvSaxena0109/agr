Using already trained model. 

Runing
python run_classifier.py  <br />
--task_name=cola  <br />
--do_train=true  <br />
--do_eval=true  <br />
--do_predic <br />
--data_dir=./data/ 
--vocab_file=./cased_L-12_H-768_A-12/vocab.txt  <br />
--bert_config_file=./cased_L-12_H-768_A-12/bert_config.json  <br />
--init_checkpoint=./cased_L-12_H-768_A-12/bert_model.ckpt  <br />
--max_seq_length=128  <br />
--train_batch_size=32  <br />
--learning_rate=2e-5  <br />
--num_train_epochs=3.0  <br />
--output_dir=./bert_output/  <br />
--do_lower_case=False <br />

export TRAINED_MODEL_CKPT=./bert_output/model.ckpt <br />

python run_classifier.py  <br />
--task_name=cola  <br />
--do_predict=true  <br />
--data_dir=./data  <br />
--vocab_file=./cased_L-12_H-768_A-12/vocab.txt 
--bert_config_file=/cased_L-12_H-768_A-12/bert_config.json  <br />
--init_checkpoint=$TRAINED_MODEL_CKPT <br />
--max_seq_length=128 
--output_dir=./bert_output <br />

test_result.tsv  <br />
