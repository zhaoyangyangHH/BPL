# Bootstrapped Policy Learning for Task-oriented Dialogue through Goal Shaping <br />


This document describes how to run the simulation of BPL Agent.  <br />

## Requirements

python: 2.7  <br />
and pytorch  <br />
 
## DATA

All the data is located in the folder _./src/deep_dialog/data_domains_, which includes the movie, restaurant, and taxi domains, following the paper 'Dialogue Environments are Different from Games: Investigating Variants of Deep Q-Networks for Dialogue Policy.' Additionally, the platform is based on the paper 'Microsoft Dialogue Challenge: Building End-to-End Task-Completion Dialogue Systems.


__Knowledge Bases__ <br />
movie domain: movie_kb.1k.p <br />
resturant domain: restaurant.kb.nondup.v1.p <br />
taxi domain: taxi.kb.v2.nondup.p <br />

__User Goals__ <br />
movie domain: user_goals_first_turn_template.part.movie.v1.p <br />
resturant domain: user_goals_first.v1.p <br />
taxi domain: user_goals_first.v4.p <br />

__NLG Rule Template__ <br />
dia_act_nl_pairs.v6.json  <br />

__Dialog Act Intent__ <br />
dia_acts.txt <br />

__Dialog Act Slot__ <br />
slot_set.txt <br />


## Parameter

We have introduced those parameters in the code.

ta_movie/slot_set.txt \ <br />
	--act_set ./deep_dialog/data_movie/dia_acts.txt \ <br />
	--dict_path ./deep_dialog/data_movie/slot_dict.v1.p \ <br />
	--nlg_model_path ./deep_dialog/models/nlg/movie/lstm_tanh_[1533529279.91]_87_99_199_0.988.p \ <br />
	--nlu_model_path ./deep_dialog/models/nlu/movie/lstm_[1533588045.3]_38_38_240_0.998.p \ <br />
	--diaact_nl_pairs ./deep_dialog/data_movie/dia_act_nl_pairs.v7.json \ <br />
	--dqn_hidden_size 80 \ <br />
	--experience_replay_pool_size 10000 \ <br />
	--episodes 500 \ <br />
	--simulation_epoch_size 100 \ <br />
	--write_model_dir $save_path \ <br />
	--run_mode 3 \ <br />
	--act_level 0 \ <br />
	--slot_err_prob 0.0 \ <br />
	--intent_err_prob 0.0 \ <br />
	--batch_size 16 \ <br />
	--warm_start 1 \ <br />
	--warm_start_epochs 120 \ <br />
	--epsilon 0.00 \ <br />
	--gamma 0.95 \ <br />
	--dueling_dqn 0 \ <br />
	--double_dqn 0 \ <br />
	--distributional 0 \ <br />
	--icm 0 \ <br />
	--per 0 \ <br />
	--noisy 0 <br />
done  <br />
 
For different domains, the bash files are all stored in the _`./script`_ directory.   <br />
For different combinations of BPL and baseline models, the choice can be made according to the remarks in the code for different simulation_epoch_train methods. <br />



## Reference


@inproceedings{zhao2024emnlp,  <br />
  title={Bootstrapped Policy Learning for Task-oriented Dialogue through Goal Shaping},  <br />
  author={Zhao, Yangyang and Niu, Ben and Dastani, Mehdi and Wang, Shihan},  <br />
  booktitle={EMNLP},  <br />
  year={2024}  <br />
}  <br />


@inproceedings{wang2019dialogue,  <br />
  title={Dialogue environments are different from games: Investigating variants of deep q-networks for dialogue policy},  <br />
  author={Wang, Yu-An and Chen, Yun-Nung},  <br />
  booktitle={2019 IEEE Automatic Speech Recognition and Understanding Workshop (ASRU)},  <br />
  pages={1070--1076},  <br />
  year={2019},  <br />
  organization={IEEE}  <br />
}  <br />


@article{li2018microsoft,   <br />
  title={Microsoft Dialogue Challenge: Building End-to-End Task-Completion Dialogue Systems},   <br />
  author={Li, Xiujun and Panda, Sarah and Liu, Jingjing and Gao, Jianfeng},   <br />
  journal={arXiv preprint arXiv:1807.11125},   <br />
  year={2018}   <br />
}  <br />

