import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scan=new Scanner(System.in);
        int n=scan.nextInt();
        int a[]=new int[100];
        int index=-1;
        index=-1;
        //Entering the values in the array
        for(int i=0;i<n;i++){
            a[i]=scan.nextInt();
        }
        
        int x=scan.nextInt();
        //Sorting the array
        for(int i=0;i<n;i++){
            for(int j=0;j<n-i-1;j++){
                if(a[j]>a[j+1]){
                    int tem=a[j];
                    a[j]=a[j+1];
                    a[j+1]=tem;
                }
            }
        }
        
        int beg,last,mid;
        beg=0;
        last=n-1;
        while(beg<=last){
            mid=(beg+last)/2;
            if(x==a[mid]){
                index=mid;
                break;
            }
            else if(x>a[mid]){
                beg=mid+1;
            }
            else{
                last=mid-1;
            }
        }
  
//Printing the middele number
       System.out.printf("%d",index);

    }
}
