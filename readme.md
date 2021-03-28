# Readme
> I am keeping upgrade, so the code may change everyday.

## Environment

- windows 10 (We use win32 API to operate the little knight and get screen shot)
- python 3.8.8
- python liberary: find in requirments.txt
- Hollow Knight
- HP Bar mod for Hollow Knight (In order to get the boss hp to calculate the reward, please find the mod in /hollow_knight_Data/, and then copy the mod file to the game folder)
- CUDA and cudnn for tensorflow

## Usage

- Now I only write train.py but no test.py(the file is just test some base functions not for model), your can write it by yourself if you get a good model.
- Adjust the game resolution to 1920*1017 (If not, you have to rewrite hp calculate function by yourself)
- Run train.py
- Keep the game window at the forefront (Since I cannot send keyboard event in the background, I tried PossMassage() in win32 API, but it did not work well.
                                         If you have any idea about sending keyboard event in the background, please let me know)
- Let the little knight stand in front of the statue of the boss in the godhome
- Press F1 to start train. (Also you can use F1 to stop trainning)


## Code structure
- Most train configuration is in train.py
- Agent.py gets output actions from our model
- DQN.py is the learning algorithm
- Model.py defines the model we use
- ReplayMemory.py defines the experience pool for learning
- test.py is useless, I use it to test basic functions and fix bugs

- Files in /Tool/ is for other functions we may use
- Actions defines actions for little knight and restart game script
- GetHp help us calculate our hp and boss hp (it may have some bugs, you can fix it by yourself)
- SendKey is the API we use to send keyboard event to windows system.
- UserInput is an useless file, which I used it to train my model manually.
- WindowsAPI is used to get screenshot of the game, and key_check() is used to check which key is pressed.
- Helper defines [Reward Jugment] fucntion, and other functions we may use

## Changes

- Add deley reward of an action

- Make the mdoel output an action sequence

- Use two models to output actions. One is for moving and the orther is for attack/jump/skill

- ...