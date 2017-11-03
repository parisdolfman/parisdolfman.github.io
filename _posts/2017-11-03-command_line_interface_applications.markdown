---
layout: post
title:      "Command Line Interface Applications"
date:       2017-11-03 16:35:31 +0000
permalink:  command_line_interface_applications
---

Command Line Interface applications are programs that are interacted with via terminal and shell. They are very basic and operate through ASCII output and input. In the root of a CLI application directory is a structure which contains folders and directories. Top-level directories are directories like bin/ (binary) which contains the code to run our program, lib/ (library) which contains where the majority of our code goes, config/ (configuration) where our code environment goes, and spec/ where our test code goes. 
Bin is short for binary and is where executable files go. Executable files are the files which contain the instructions for our computer and are written in a way that the computers OS or application can understand and use. All executable files have to start with ***#!/usr/bin env ruby*** which is called a shebang line. 
The shebang line tells the shell which interpreter to use for the remainder of the file. 
A CLI program will continue accepting input from a user until exited or by pressing ALT+C (for windows). CLI programs operate through what is called a program loop. What this means is that the program will continue to sift through a menu in a rotating fashion continually until it is closed. 
Here is an example of a main application loop:
1) What game would you like to play? I accept Tic Tac Toe or Checkers
2) program accepts user input: Tic Tac Toe
3) What number box would you like your first move to be in? I accept 1-9.
4) program accepts user input: 3
5) the loop continues in this fashion until the game is finished. When finished, loop begins again.
6) What game would you like to play? I accept Tic Tac Toe of Checkers. 
