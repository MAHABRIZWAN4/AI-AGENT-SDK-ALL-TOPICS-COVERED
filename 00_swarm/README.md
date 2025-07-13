
# What is Swarm ? 

Swarm ek experimental system tha jahan multiple AI agents ek team ki tarah kaam karte hain.
Yani har agent apna kaam karta hai aur agar kisi aur ko kaam dena ho to woh us agent ko "handoff" kar deta hai.

## ☕ Swarm (Pure System/Team Example):
Ek coffee shop jahan:

- Order Taker Agent

- Coffee Maker Agent

- Snack Maker Agent

- Cashier Agent

Sab agents ek team (Swarm) ki tarah kaam kar rahe hain.
Har agent apna specific kaam independently kar raha hai.

🧠 Swarm = Team of agents working together with their own tasks

# What is Handoff ?

Handoff ek process hota hai jisme ek agent doosray agent ko kaam ya control transfer karta hai jo us kaam ke liye zyada suitable hota hai.

## 🔁 Handoff (Task Transfer Example):
Ab customer ne bola:

"Mujhe coffee aur sandwich chahiye, aur main card se pay karunga."

- Ab dekho kaise handoff hota hai:
Order Taker Agent ne order liya

- Usne coffee ka kaam Coffee Maker ko handoff kiya

- Aur snack ka kaam Snack Maker ko handoff kiya

Jab sab ready ho gaya, to customer ko Cashier Agent ke paas bhej diya for payment (last handoff)

## Difference between Swarm & Handsoff :

Swarm = Puri team

Handoff = Team ke members ke darmiyan kaam ka transfer

# OpenAI Agents SDK kya hai?

Ye Swarm ka upgrade version hai — jo production ke liye ready hai.
Isme zyada features hain jese routing, parallel kaam karna, feedback lena, etc.

Ye ek powerful toolkit (SDK) hai jo developers ko help karta hai multiple AI agents ke system banane me — jahan har agent apna role play karta hai aur mil kar complex kaam complete karte hain.

####  <i> SDK = Software Development Kit </i>

So, OpenAI Agents SDK = Ek special toolkit to build and manage AI agent systems easily.

# Anthropic Design Patterns kya hain?

Ye ek set of ideas (design styles) hain jo batate hain ke AI agents system ko kaise design karna chahiye — taake wo smart, organized aur efficient kaam karein.

Yani agar tum AI agents se koi complex kaam karwana chahti ho, to ye patterns tumhein guide karte hain kaam ko todne, baantne, aur improve karne ke tareeqe.

### 5 Important Patterns (with daily life examples):

#### **<i>1.Prompt Chaining (Chain Workflow)</i>**
Bara kaam chhote steps me todna – jese ek chain.

#### 📦 Example: Cake banana

1.  Ingredients lana
2. Mix karna
3. Bake karna
4. Serve karna
– Har step ek agent karega. Sab milke final result banate hain.

#### **<i>2.Routing</i>**
Har kaam us agent ko dena jo usme expert hai.

##### 📞 Example: Call center

Customer ne complaint ki. General agent ne dekha ke issue technical hai — to usne technical agent ko route (handoff) kar diya.

#### **<i>3.Parallelization</i>**

Multiple kaam ek sath karwana — time save karne ke liye.

##### Example:

Tum dinner bana rahi ho:
1. Tum roti banati ho
2. Baji salan
3. Bhai salad

Sab kaam ek sath parallel chal rahe hain.

#### **<i>4. Orchestrator-Workers</i>**

Ek orchestrator (leader) agents ko kaam divide karta hai, baqi workers usay complete karte hain.

##### Example:

School project me:

1. Tum leader ho

2. Tum kaam divide karti ho:

3. A ko presentation

4. B ko research

5. C ko design

Tum sabka kaam ikatha karke final result deti ho.

#### **<i>5. Evaluator-Optimizer</i>**

Ek agent ka kaam hota hai check karna ke baqi agents kaam sahi kar rahe hain ya nahi — aur suggestions dena.

##### Example:

Teacher sab students ke assignments check karti hain

Galti batati hain

Suggest karti hain kya improve karein
Ye agent system me quality control hota hai


