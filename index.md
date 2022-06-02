## Fundamentals of Arthroscopic Surgery Training: a reinforcement learning exploration and benchmark

**FASTRL** is a a set of benchmark tasks used in surgical training which are adapted to the reinforcement learning setting for the purpose of training agents capable of providing assistance to the surgical trainees. The benchmark is provided with the purpose of exploring the domain of human-centric teaching agents within the learning-to-teach formalism.

**FASTRL** uses the Arthros$\circledR$ FAST (Fundamentals of Arthroscopic Surgery Training) simulator provided by Virtamed AG 
to evaluate the RL pipeline. The simulation provides a number of educational navigation and manipulation tasks performed within a hollow dome structure in accordance with the Fundamentals of Arthroscopic Surgery Training (FAST) training problem developed by major American orthopaedic associations ABOS (American Board of Orthopaedic Surgery), AAOS (American Academy of Orthopaedic Surgeons) and AANA (Arthroscopy Association of North America).

### Benchmark Tasks

The benchmark contains three tasks: *ImageCentering* consisting of image centering and horizoning, *Periscoping* and *TraceLines* consisting of line tracing. These tasks consist of guiding the tip of the virtual endoscope to various locations marked by an avatar displaying visual cues. The goal is to orient the endoscope in such a way as to comply with the cues and center the image of the avatar in the field of view of the endoscope camera.

#### *ImageCentering*
In *ImageCentering* the tip of the arthroscope (the Agent) must visualise the target avatar by centering the target in the field of view of the arthroscope. 

#### *TraceLines*
In *TraceLines*, the avatar will follow multiple splines, during which the tip of the arthroscope (the Agent) must follow the avatar. 


<p align="center">
  <img width="854" height="480" src="https://user-images.githubusercontent.com/50180899/171658310-fe85fa4b-2598-4370-90f5-ac5617c034ff.mov">
</p>




#### *Periscoping*

In *Periscoping* the tip of the arthroscope (the Agent) must visualise the target avatar using angeld optics. 

<p align="center">
  <img width="854" height="480" src="https://user-images.githubusercontent.com/50180899/171658295-2181e551-3048-45f8-a541-0bf73b1669e4.mov">
</p>



### Training an RL Agent Asing ML-Agents

 The Unity Machine Learning Agents Toolkit ([ML-Agents](https://github.com/Unity-Technologies/ml-agents)) is an open source toolkit which provides PyTorch implementation of many known RL algorithms such as PPO, SAC and GAIL. 

The following command shows how to train a simple PPO model (described in the config file `configs/fast_ppo_config.yaml` provided in the repo) for the *Periscoping* environment (`--env pe/pe.x86_64`also provided in the repo)

```
mlagents-learn configs/fast_ppo_config.yaml --env pe/pe.x86_64 --results-dir path/to/results --run-id my_experiment_name
```

To learn more about different provided environment please see [Environments](#environments)

### Training an RL Agent Using Stable Baselines3

[Stable Baselines3](https://github.com/DLR-RM/stable-baselines3) is another popular RL open source project providing a set of reliable implementations of reinforcement learning algorithms in PyTorch. 

The following is an example of how to train a PPO agent (described in the config file) for the *Periscoping* environment.
```
python sb3_main.py --ml_config_path configs/config_sb3.yaml --env ../builds/ic/ic.x86_64 --task_name ImageCentering -n ic

```
### Training Configs

#### ML-Agents Configs

#### Stable Baseline Configs

### Environments

### Environment Configurations
