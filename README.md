## **HW 2: Agent-Based Modeling of Pandemic Spread**
Name: Rongjia (Jasmine) Zhou

Email: rzhou73@emory.edu

Question number: Homework 2

### **Results/answers to the discussion items**
#### Analyze how p and q affect the infection peak, the time to the peak, and the total number of agents ever infected. How much do individual runs differ from the average? In how many runs does the outbreak die out early?
![SIR curve](sir_simulations_combination.png)

**SIR simulation results — 20 runs per parameter combination**

| p | q | Average peak infected | Average time to peak | Average ever infected by step 300 | Early die-out runs | Mean SIR SD |
|---:|---:|---:|---:|---:|---:|---:|
| 0.15 | 0.02 | 58.55 | 127.05 | 182.00 | 0 | 15.08 |
| 0.15 | 0.04 | 19.35 | 70.55 | 84.20 | 3 | 22.28 |
| 0.30 | 0.02 | 89.10 | 71.60 | 198.85 | 0 | 7.08 |
| 0.30 | 0.04 | 45.05 | 74.65 | 177.20 | 0 | 12.92 |

- Increasing p increased the average total number of agents ever infected. At q = 0.02, doubling p increased the average peak infected from 59 to 89 agents and total infection from 182 to 199 agents. The average time to reach the peak also reduced from 127 time steps to 72 steps. This trend holds true for doubling p at q = 0.04, where the peak and total infections also increased. The average time to peak, however, increased as p increased for q = 0.04. 
- Meanwhile, increasing q reduced the outbreak severity. At p = 0.15, doubling q reduced the average peak infected from 59 to 19 and total infected from 182  to 84. At p = 0.3, doubling q reduced the peak from 89 to 45 and total infections from 199 to 177. The effect on peak timing is not obvious, given that doubling q reduced time to peak for p = 0.15 but slightly deplayed the time to peak for p = 0.3.
- Based on the mean SIR standard deviations (variation across the entire SIR curves), we can see the individuals runs are fairly consistent and resembles the average. The variation between runs was greatest at p = 0.15 and q = 0.04 (SD = 22.28). The SIR curves were most consistent when infection probability (p) was high and recovery probability (q) was low. 
- Assuming 'early' means after 100 time steps zero infected agents were reached, it only occurred when p = 0.15 and q = 0.04 at 3 of 20 runs (~15%). 

#### Which parameter controls the maximum number of simultaneously infected agents, which determines whether the healthcare system is overwhelmed?
![SIR curve of social distancing](sir_distancing_comparison.png)
- The maximum number of simultaneously affected agents is determined by infection probability (p), recovery probability (q), and movement probability (m). A high p, low q, and m close to 1 would cause the most severe outbreak. 
- The peak infection count determines whether the healthcare system is overwhelmed because it creates the greatest burden. To truly determine healthcare overload, additioanl information is needed (e.g., the capacity of the hospital).

#### Discuss how stricter or more relaxed distancing affects the epidemic.
![Effect of movement probability on infection peak and peak timing](distancing_vs_movement_prob.png)

- Stricter social distancing (lower m) delays the average time to peak because it reduces transmission opportunities. It also leads to smaller infection scale and lower average peak infections. Relaxing distancing is generally associated with a faster and larger outbreak, but the increase is not consistent for all m (decreased from 87.5 for m = 0.6 to 72.6 for m = 1.0).

### **Discussion (Hypothesis revisited)**
My hypothesis is largely supported by the experiments, although there are some minor deviations. 

- i) The height of the infection peak is lowered and the timing of the infection peak is delayed with reduced movement. At m = 0.5, the average peak decreased from 89.10 to 78.95, while the average time to peak increased from 71.60 to 73.85 steps. At m = 0.1, the average peak was 22.05 at step 124.80. However, less movement does not consistently lower peaks. m = 0.6 produced higher average peak than m = 1.0, which makes my initial hypothesis partially supported. 

- ii) Individual runs varying slightly are partly supported. The variation between individual runs is correct, but some differences existed. The average does not always exactly match individual runs. 

- iii) The average agent-based curves broadly resembles the SIR curves. Infection generally rose and then declined, while recovered counts increased. However, the susceptible population decreased or remained constant instead of slightly rising at later time points. 

### **AI statement**
Chat-GPT was used to complete this homework. The full chat is available at: https://chatgpt.com/share/6ad03d41-0ea0-83ea-8ecc-dec4af5bdbaf

### **Instructions to run the code**
Install relevant dependencies through:

python3 -m pip install -r requirements.txt