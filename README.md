# Taxi Q-Learning Agent 🚕

A **Reinforcement Learning agent** that solves the **Taxi-v3** environment from OpenAI Gym using **Q-Learning**. The agent learns to navigate a 5x5 grid, pick up passengers, and drop them off efficiently, minimizing travel steps while maximizing rewards.

![Taxi Agent GIF](taxi_agent_behavior.gif)

---

## 🏎 Features

- Trains over **2,000 episodes** using **epsilon-greedy Q-Learning**
- Learns an **optimal policy** for taxi navigation
- Records **episode rewards** (`episode_returns`) and **Q-values** (`q_table`)
- Test episode visualization using **frames → GIF**
- Efficient: solves an episode in **≤16 actions**

---

## 🎮 Environment

- **Gym Environment:** `Taxi-v3`
- **Observation Space:** 500 discrete states  
- **Action Space:** 6 discrete actions:
  - 0: South
  - 1: North
  - 2: East
  - 3: West
  - 4: Pick up passenger
  - 5: Drop off passenger
- **Reward System:**
  - -1 per step
  - +20 for successful dropoff
  - -10 for illegal pickup/dropoff

---

## ⚙️ Installation

```bash
pip install gymnasium numpy imageio
````

---

## 💻 Usage

### 1. Train the Agent

```python
# Run this to train the agent and save Q-table
python train_taxi.py
```

### 2. Test the Learned Policy & Generate GIF

```python
# Run this to test the policy and generate a GIF
python test_taxi.py
```

### 3. Display GIF in Notebook (Optional)

```python
from IPython.display import Image, display
display(Image('taxi_agent_behavior.gif'))
```

---

## 📈 Results

* **Episode total reward (test):** ≥ 4
* Taxi navigates efficiently to pick up and drop off passengers in ≤16 actions.
* Q-learning converges to an effective policy, as visualized in the GIF.

---

## 🧠 How It Works

1. Initialize a **Q-table** with zeros.
2. Train the agent over episodes using **epsilon-greedy Q-Learning**.
3. Update Q-values according to the reward and max future Q-value.
4. Derive the **optimal policy** by taking the argmax of Q-values.
5. Test the policy and record frames to create a GIF.



