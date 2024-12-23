# Lecture 28 Special Topics III (Python Pickling)

1. Questions
2. What is hackable?
    1. Everything
    2. Security is important for physical safety
3. Security Principles
    1. Know your threat model and what resources they have
    2. Common Assumptions for attackers
        1. has the resources required to mount the attack
        2. can get lucky
    3. Trusted Computing Base
        1. The components of a system that the security relies upon
        2. generally make it smaller
        3. KISS principle: Keep it simple, stupid
    4. Consider Human Factors
        1. if a security system is unusable, it will be unused
        2. C and C++ is not memory safe
    5. Security is Economics
        1. Cost/Benefit analysis, defense should be proportional to attack
        2. More security costs more
        3. $10 lock on $1 item
    6. Detect if you can’t prevent
        1. deterrence: stop attack before it happens
        2. prevention: stop attack as it happens
        3. detection: learn there was an attack afterwards
        4. response: do something about the attack
            1. mitigation and recovery
                1. have resources like emergency food supply
                2. offsite backups
    7. Defense in Depth
        1. multiple types of defenses should be layers together
    8. Least privilege
        1. consider what permissions a program needs to do its job correctly
    9. Separation of Responsibility
        1. considering requiring multiple parties to work together to exercise it
    10. Exercise Complete Mediation
        1. ensure that every access point is monitored and protected
    11. The time-of-check to time-of-use
    12. Shannon Maxim
        1. the enemy knows the system
    13. Using fail-safe defaults
        1. balancing security with usability
    14. Design in security from the start
        1. start with security when you start
4. What is a system call?
    1. Languages and memory
        1. Pieces of information are stored at an address within a computer memory
    2. User vs Administrator
        1. only admin can access the “vital organs” of your computer
5. Serialization
    1. Pickling is the process where a Python object hierarchy is converted into a byte stream
    2. byte stream store state of object
    3. you want to save your program state
    4. reduce method
        1. intended to reconstruct objects
    5. unpacking and repacking in python
    6. Vulnerabilities in pickle
        1. attack provides malicious code to be deserialized
    7. Detection and Defenses: Serialization
        1. can an attacker ever provide input to these functions
        2. don’t unpickle untrusted data