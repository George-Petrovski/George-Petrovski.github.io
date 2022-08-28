---
title: Coding Challege 3
subtitle: Programmers Coding Challege Develop Features
layout: post_detail
date-created: 2021-08-11
date-edited: 
img: dreams.png
thumbnail: 2021-08-11-coding-challenge-develop-feature-thumbnail.jpg
alt: image-alt
category: [Post, Study, Programmers]
description: Coding Test-Stack/Queue | Q1 Develop Features
comments: true
---

# Coding Challege-Stack/Queue | Q1 Develop Features

## Coding Challege Link
[Programmers Coding Challege: Stack/Queue - Q1 Develop features](https://programmers.co.kr/learn/courses/30/lessons/42586?language=java){:target="_blank"}

## Solution

```Java
package StackQueue;

import java.util.LinkedList;
import java.util.Queue;

public class Q1DevelopeFunction {
	
	public static void main(String[] args) {
		 System.out.println(solution(new int[] { 93, 30, 55 }, new int[] { 1, 30, 5 }));
		 System.out.println(solution(new int[] { 95, 90, 99, 99, 80, 99 }, new int[] { 1, 1, 1, 1, 1, 1 }));
		 System.out.println(solution(new int[] { 20, 99, 93, 30, 55, 10 }, new int[] { 5, 10, 1, 1, 30, 5 }));
		 System.out.println(solution(new int[] { 96, 99, 98, 97 }, new int[] { 1, 1, 1, 1 }));
		 System.out.println(solution(new int[] { 40, 93, 30, 55, 60, 65 }, new int[] { 60, 1, 30, 5, 10, 7 }));
		 System.out.println(solution(new int[] { 93, 30, 55, 60, 40, 65 }, new int[] { 1, 30, 5, 10, 60, 7 }));
	}
	
	public static int[] solution(int[] progresses, int[] speeds) {
		// Declare Queue 
		Queue<Integer> queueAnswer = new LinkedList<>();		
		Queue<Integer> queueProgress = new LinkedList<>();
		Queue<Integer> queueTemp = new LinkedList<>();
		
		// Array to Queue (progresses -> queueProgress)
		for (int i : progresses) {
			queueProgress.add(i);
		}
		
		// 1. Queue Retrieve 
		while (queueProgress.size() != 0) {
			int count = 0;
			int j = speeds.length - queueProgress.size();
			Boolean decision = false;
			
			// queueTemp = progress + speed
			for (int i : queueProgress) {
				queueTemp.add(i + speeds[j]);
				j++;
			}
			
			queueProgress.clear();
		
			if (queueTemp.peek() >= 100) {
				decision = true;
			}
			
			for (int i : queueTemp) {
				if (i < 100 || decision == false) {
					queueProgress.add(i);
					decision = false;
				} else {
					count++;
				}
			}
			
			queueTemp.clear();
			
			if (count != 0) {
				queueAnswer.add(count);
			}
		}

		// Convert Queue to int[]
		int[] answer = new int[queueAnswer.size()];
		for (int i = 0; i < answer.length; i++) {
			answer[i] = queueAnswer.remove();
		}	
		
        return answer;
    }
}

```