# Edabit-TrackTheRobotGame
My solution for TrackTheRobot problem on edabit.

QUESTION : https://edabit.com/challenge/g88PKZrCY6sWPBva7

A robot has been given a list of movement instructions. Each instruction is either left, right, up or down, followed by a distance to move. The robot starts at [0, 0]. You want to calculate where the robot will end up and return its final position as an array.

To illustrate, if the robot is given the following instructions:

new string[] { "right 10", "up 50", "left 30", "down 10" }
It will end up 20 left and 40 up from where it started, so we return int[] { -20, 40 }.

                                                          MY CODE
                                                          
using System;

public class Program
{
	static int[] coords = new int[10];
	static int x = 0;
	static int y = 0;
    public static int[] TrackRobot(string[] instructions) {
			string[] word = new string[10];
				for(int i = 0; i < 4; i++) {
				word = instructions[i].Split(' ');
				switch(word[0]) {
					case "right":
						x += Convert.ToInt32(word[1]);
						break;
					case "left":
						x -= Convert.ToInt32(word[1]);
						break;
					case "up":
						y += Convert.ToInt32(word[1]);
						break;
					case "down":
						y -= Convert.ToInt32(word[1]);
						break;
				}
			}
			coords[0] = x;
			coords[1] = y;
			return coords;
	}
}
