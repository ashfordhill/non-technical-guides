# Cost of Library Maintenance

## Motivation

When trying to explain a certain technical debt to non-technical leadership that inherited a legacy project, there was confusion.

The idea of a 'library' itself can be an abstract concept to someone unfamiliar with software. 

Here, I attempt to illustrate what a library is and why, in the case of Library X, it is not worth the cost maintenance. 

## What is a Library?

<img src="car-diagram.png" width="300">

If an **application is a car**, then a **library is a car component**.

Imagine being in charge of building a car. Let's say you have some of the necessary components but not all of them. You don't want to manufacture the missing components from scratch, understandably. 

Instead, you:

  - Acquire the **car components (libraries)** you need.
  - Have **mechanics (software devs)** assemble it all together.


## Cost of Maintaining Library X

Library X is used within multiple applications among multiple developers.

<img src="library-sharing.png" width="300">

**Uploads** and **Downloads** each have their own pain points that may require maintenance, even if the underlying code of Library X is untouched.

Additionally, when other developers use Library X within their application's code, they may run into build issues in their application that may or may not be the 'fault' of Library X. This costs time and can cause frustration via finger-pointing between developer teams.

### Multiple Language and Schema Issues

Library X has been offered in multiple programming languages and multiple schemas for each language.

However, maintaining this becomes overwhelming quickly:

<img src="library-multiple-schemas.png" width="300">

You could in theory have a language-agnostic or schema-agnostic version of Library X. But due technical reasons, this involves a tradeoff involving too much complexity for the value Library X offers.

### The Value of Library X

Library X attempts to solve multiple problems at once. Unfortunately the problems it does solve are quite trivial.

The value Library X provides from a software perspective is like **overpaying for a bundle windshield wipers, battery and air filter**:

<img src="cost-of-parts-bundle.png" width="300">

Also pretend that the mechanics dislike manufacturers of these bundled parts.

## Recommendations

Offer standalone solutions that **don't** mix with other team/developer's coding projects. These solutions may only need to utilize 1 programming language. This prevents:

  - Being involved or a potential source of culpability when other developers cannot build their code. 
  - Reducing the amount of **Upload** and **Download** failures described above.
  - The need to have developers proficient in multiple programming languages.

In the car analogy, this is like **offering a car accessory for an already built car** instead of helping build the car.

## A Solution

For fun, here is a very simplified posisble solution to the original problem involving Library X:


### Before

<img src="solution-before.png" width="300">

### After

<img src="solution-after.png" width="300">