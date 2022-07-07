# TestGit
Git的使用
package com.example.demo;
import java.util.Scanner;

public class FindFriendsDemo {
    public static void main(String[] args) {
        int[] position = inputAndProcess();
        print(position);
    }

    static void process(int[] height, int index, int[] position){
        for (int i = index + 1; i < height.length; i++) {
           if (height[i] > height[index]){
               position[index] = i + 1;
               return;
           }
        }
        position[index] = 0;
    }

    static int[] inputAndProcess(){
        // 完成初始化
        Scanner sc = new Scanner(System.in);
        int[] height =new int[sc.nextInt()];// 小朋友身高
        for (int i = 0; i <height.length; i++) {height[i]=sc.nextInt(); }
        int[] position = new int[height.length];// 小朋友的好朋友的位置信息
        for (int i = 0; i < height.length; i++) {process(height,i,position);}
        return position;
    }

    static void print(int[] position){
        for (int i = 0; i < position.length; i++) {System.out.print(position[i] +" ");
        }
    }
}
