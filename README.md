# 📘 Overview

During the **Fab26 Event**, an interesting workshop titled

**“How to Code Almost Anything for Hardware with LLMs”** was conducted by **Feng Lei (Leon)** from **Seeed Studio** — a Fab Academy 2025 graduate from **Chaihuo Makerspace**.

I attended the workshop along with one of my students, **Abin Mathew**, who was excited about the idea of *“coding without coding”* 🙂

The workshop started with the usual workflow — using tools like **ChatGPT**, **Claude**, and **Gemini** to generate embedded code and uploading it using traditional toolchains. The hardware used throughout the session was **Seeed Studio’s Wio Terminal**, which can be programmed using the Arduino IDE.

Hardware details and setup guide:

👉 https://wiki.seeedstudio.com/Wio-Terminal-Getting-Started/

Leon demonstrated how LLMs can assist in writing firmware, understanding libraries, and speeding up development. But midway through the workshop, he introduced something truly impressive — an **Agentic AI workflow for embedded systems**.

This AI system was able to:

- Learn about the hardware automatically
- Download the required toolchains
- Compile the firmware
- Upload the code
- Debug issues

—all from a **simple natural language prompt**.

Watching an AI handle the full embedded development workflow by itself was amazing.

Due to Wi-Fi issues, many participants left the workshop midway. However, my student and I stayed until the end, completed all the tasks given by Leon, and achieved some great results on the Wio Terminal.

This experience clearly showed how, in the future, engineers will spend more time on **designing systems and product ideas**, while AI handles most of the toolchain setup and low-level programming.

In this repository, I’ve linked:

- All necessary files
- Example workflows
- Reference videos
- Notes and learnings

to help students and makers start using AI effectively in embedded systems.

---

# Fab25 Workshop Demos

### Blink program by Claude code with Wio terminal (usual ways of AI in coding )

![Demo 1](Media/Demo1.mp4)



### Blink code by Augment (agentic plat form like cursor ai)  with Wio terminal 

![alt text](Media/agument-code-vscode.png)
A VS code extension needed to be installed for this demo, which is by Augment Ai, and sign in with your own account required.

![Demo 2](Media/Agent-Blink-En.mp4)

**Prompt:**
```
Please implement WIo Terminal Blink acoring to @rule_en.md requirements
```



### Here is another demo with Augment using chinese language

![Demo 3](Media/Agent-Demo.mp4)


### here is a simple snake game on wio terminal built using agentic AI workflow

![Snake game on wio terminal](Media/Simple_snake-game.mp4)

**Prompt:**
```
lets build a simple snake game, use the joystick to navigate and button A for resetting
```


### References  
 - [Wio Terminal rule_en.md file](Media/rule_en.md)
 - [Wio Terminal wiki](https://wiki.seeedstudio.com/Wio-Terminal-Getting-Started/)
 - [Augment Code](https://www.augmentcode.com/)
 - [claude code](https://claude.com/product/claude-code)
 [Leon's Fab25 Workshop Slides](https://docs.google.com/presentation/d/1A9xDLNIsvHBhZPCZVh_9QFkY29XSWMen/edit?usp=sharing&ouid=112880891325260851622&rtpof=true&sd=true)
 [Fab25 Workshop Teahing Guide](https://docs.google.com/document/d/1xDxKDptkMbUgF7MD0EHMpGoiqyAZdZ0BLgn_MCSyt-w/edit?usp=sharing)
---

# Setting up your own AI agent for your own Embedded system Hardware

after reaching out to leon about setting up a custom agentic Ai workflow for our own hardware, he shared a detailed document on how to do it. 

you can find it here:
[Leon's Ai Guide](Guidlines/Leons_ai_guide.md)

Check out the above guide for setting up your own AI agent for your own Embedded system Hardware. thanks to Leon for sharing this guide. any doubts can be clarified with me in mattermost or use chatGPT or any AI you prefer  :)


### 🚀 Happy coding (without coding!)