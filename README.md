# CLUTCH - Introduction

*"Here lies one whose name was written in water."*

---

![](https://img.shields.io/badge/Language-C++-blue) ![](https://img.shields.io/badge/Standard-C++20-blue) ![](https://img.shields.io/badge/Dependencies-STL_Only-green) ![](https://img.shields.io/badge/License-MIT-yellow) ![](https://img.shields.io/badge/Platform-Any-lightgrey)

**CLUTCH** is a collection of modules that are considered expendable and formerly a part of LAUNCH.  
The original introductions of the modules in the README of LAUNCH are listed below.

### \<caref\>

- What does the name mean?  
**-** **C**lever & **A**utomatic **Ref**erence
- What can \<caref\> do?
```cpp
launch::caref<int> observer;
// observer - construct
{
    launch::caref<int> owner(new int(42));
    // owner - construct
    std::cout << "Owner: " << *owner << "\n";
    observer = owner;
    // observer - observing
    std::cout << "Observer: " << *observer << "\n";
    owner.move(observer);
    // owner - move ownership to observer
}
// owner - destruct
std::cout << "Observer outside:" << *observer << "\n";
// as you can see - the observer is still alive!
```
- Expected output:
```
Owner: 42
Observer: 42
Observer outside: 42
```

### \<lidevec\> (LEISURE feature)

- What does the name mean?  
**-** I don't know either. Perhaps you can think of that as **Li**st / **De**que / **Vec**tor, I think?
- What can \<lidevec\> do?  
Well, it's just a `std::forward_list`, but **faster**. To be accurate, it's **dozens** **of** **times** **faster**.  
If you're using or going to use C++26, then don't use `lidevec`. Instead, use `std::hive`. `lidevec` does **not** support iterators while `std::hive` do.

---

<sub>Author: Arcsin Studios<br>License (of this document): CC BY-SA 4.0</sub>