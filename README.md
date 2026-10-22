# Minecraft in Python in a Nutshell 🧱

A fully functional 3D Minecraft clone compressed into **exactly one line of Python code**. Build and destroy blocks in a 3D world with a first-person controller.

No `node`, `npm`, `git`, or heavy engines required. **Just pure Python.**

---

## 🚀 How to Run

You only need **Python 3** installed on your computer to run this game.

### 1. Install the 3D Engine
Open your terminal (Command Prompt, PowerShell, or Terminal on Mac/Linux) and install the lightweight 3D engine dependency:
```bash
pip install ursina
```

### 2. Run the Game
Execute the single-line script directly using Python:
```bash
python main.py
```

---

## 🎮 Controls

* **`W`, `A`, `S`, `D`** : Move around
* **`Spacebar`** : Jump
* **`Left Mouse Click`** : Place a new block
* **`Right Mouse Click`** : Destroy a block
* **`Escape (Esc)`** : Exit the game

---

## ⚙️ The One-Liner Source Code

This is the entire game logic packed inside `main.py`:

```python
exec("from ursina import *; from ursina.prefabs.first_person_controller import FirstPersonController; app = Ursina(); class Voxel(Button):\\n def __init__(self, pos=(0,0,0)): super().__init__(parent=scene, position=pos, model='cube', origin_y=0.5, texture='white_cube', color=color.color(0,0,random.uniform(0.9,1)))\\n def input(self, key):\\n  if self.hovered:\\n   if key == 'left mouse down': Voxel(pos=self.position + mouse.normal)\\n   if key == 'right mouse down': destroy(self)\\nfor z in range(16):\\n for x in range(16): Voxel(pos=(x,0,z))\\nplayer = FirstPersonController(); app.run()")
```
