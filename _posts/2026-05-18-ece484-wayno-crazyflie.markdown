---
layout: post
title: "ECE484: Wayno Crazyflie Drone Racing"
date: 2026-05-18 11:00:00 -0500
excerpt: "A Crazyflie quadrotor racing project with classical PID control and reinforcement learning policies."
project: true
feature: https://latentlin2512.github.io/pic/crazyflie.png
---

<style>
  p {
    line-height: 1.8;
  }

  li {
    line-height: 1.8;
  }
</style>

<div style="text-align:center;">
  <img src="https://latentlin2512.github.io/pic/crazyflie.png" alt="Crazyflie quadrotor" style="max-width:420px;width:90%;">
</div>

## Wayno Crazyflie Quadrotor

For **ECE484: Principles of Safe Autonomy**, our team built an autonomous drone-racing pipeline for the **Crazyflie 2.1** quadrotor. The goal was to fly through a gate-based racing course quickly and reliably, both in simulation and on physical hardware.

We explored two complementary approaches: a classical **Sparse Planning + PID Control** pipeline for robust real-world flight, and a **model-free reinforcement learning** policy for high-speed simulated racing.

[Project website](https://safeautonomy-illinois-students.github.io/project-site-wayno2-0/)  
[Code repository](https://github.com/safeautonomy-illinois-students/drone-track-wayno2.git)

---

## Team

- Xiyuan Zhou
- Wenjuan Lin
- Susheendhar Vijay

---

## Classical Pipeline: Sparse Planning + PID

The classical controller uses sparse target points instead of a dense waypoint trajectory. For each gate, the planner provides key targets such as an approach point, a pass point, and optional pre-alignment points when a direct route is unsafe.

This made the controller smoother in practice: the PID controller handled low-level tracking, while the planner avoided forcing the drone to chase too many short local goals. In physical hardware tests, this pipeline completed a complex **3-lap circuit in 18.3 seconds** with stable traversal.

---

## Reinforcement Learning Pipeline

We also trained a PPO-based racing policy in a JAX-based simulation environment. The policy used a flattened observation vector containing body-frame velocity, angular velocity, orientation, current and next gate geometry, lap progress, and mission phase information.

In simulation, the RL policy reached a **3-lap completion time of 11.0 seconds**, showing much more aggressive racing behavior than the classical controller. Direct deployment to hardware exposed a sim-to-real gap caused by effects such as motor saturation and aerodynamic drag, but the result gave us a strong direction for future work on high-speed quadrotor agility.

---

## What I Learned

This project connected many parts of autonomy that usually feel separate in coursework: planning, control, simulation, reinforcement learning, system identification, and physical testing. The most valuable part for me was comparing what works beautifully in simulation with what survives on real hardware.

It also made the tradeoff between **speed** and **robustness** very concrete. The PID controller was dependable in the real world, while the RL controller showed the performance ceiling we could aim for with better sim-to-real transfer.
