# Safe Simulation of Virus, Worm, and Trojan Behavior

**Aditi Prabtani** · Class C · Batch C11  
**Diploma in Information Technology — Semester 5**  
**Gyanmanjari Innovative University**  
**Enrollment No.: 241105060103**

## 1. Introduction

Malware is software designed to perform unwanted actions. Viruses, worms, and Trojans are common categories distinguished by how they spread or conceal their purpose. This project demonstrates their high-level behavior using fictional devices and simple state changes held only in the program's memory.

## 2. Objectives

- Demonstrate the basic behavior associated with a virus, worm, and Trojan.
- Compare user-mediated copying, autonomous network propagation, and disguise.
- Produce observable simulation results without interacting with real devices or data.

## 3. Concepts

A **virus** attaches to a host and may spread when a user transfers an infected file or program. The simulation represents that user-mediated transfer as a change to an in-memory device flag.

A **worm** can propagate between connected systems without attaching to a host file. The program represents this with a breadth-first traversal of a small, fictional network graph.

A **Trojan** presents itself as something harmless or useful while concealing its intent. Here, a device receives a suspicious/disguise flag; no executable payload exists or runs.

## 4. Design and Method

The program creates six fictional devices and a fixed set of abstract connections. Each malware category is simulated on a fresh copy of this model so that its results are independent. Events are printed as they occur, followed by the number of devices marked infected or suspicious. The virus follows a short sequence of simulated file transfers; the worm visits connected devices; the Trojan records its disguise without spreading.

## 5. Safety Controls

All device records and connections are created in memory. The program does not read, create, modify, or delete files; use a network; launch processes; persist; or execute a payload. “Infection” is only a Boolean value in a fictional data structure. The simulation is intentionally non-operational and cannot infect a computer.

## 6. How to Run

Open a terminal in this project folder and run:

```text
python malware_simulator.py
```

The program uses only Python's standard library. It prints the event trace and summary in the terminal.

## 7. Observed Results

- **Virus:** 4 of 6 fictional devices are marked infected after the modeled file-transfer chain.
- **Worm:** all 6 fictional devices are reached through the connected graph.
- **Trojan:** 0 devices are marked infected; 1 device is marked suspicious to represent disguise.

The result shows how a worm can reach more connected systems in this simplified model, while virus spread depends on the specified transfer chain. The Trojan example demonstrates concealment rather than propagation. These counts illustrate the model only; they do not measure real malware behavior.

## 8. Limitations

Real malware can use many techniques, exploit vulnerabilities, and behave differently depending on its environment. This small deterministic model omits those details. It is intended for introductory comparison, not threat prediction or security testing.

## 9. Conclusion

The project demonstrates three distinct ideas: a virus spreading through a host-mediated transfer, a worm moving over connected nodes, and a Trojan disguising its purpose. Keeping the model abstract makes these differences visible while ensuring the code performs no harmful operation.

## 10. References

1. NIST Computer Security Resource Center, *Glossary: Virus* and *Glossary: Trojan Horse*.
2. CISA, *Recognize and Report Phishing* and malware awareness guidance.
3. Python Software Foundation, *Python 3 Library Reference* (collections.deque, dataclasses).
