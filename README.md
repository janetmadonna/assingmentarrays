import java.util.*;
import java.util.Arrays;
import java.util.List;
public class Main
{
	public static void main(String[] args)
	{   
	   Scanner sc=new Scanner(System.in);
	   String[] dt ={"monday 6.04","monday 9.04","monday 12.04","monday 15.04","monday 19.05","tuesday 6.04","tuesday 9.04","tuesday 12.04","tuesday 15.04","tuesday 19.04","wednesday 6.04","wednesday 9.04","wednesday 12.04","wednesday 15.04","wednesday 19.04"};
	   int[] pn={22,119,64,177,21,22,111,87,193,22,11,107,93,162,42};
	   int quit=0,menu;
	   while(quit!=1)
	   {   
	   System.out.println("1.Display day,time and passengers number \n2.Display the most popular train \n3.Diplay the least popular train \n4.Popular train between 6.04 train and 9.04 train \n5.Popular train between Monday 6.04 train and tuesday 6.04 train \n6.Find the popular train between any two train \n7.List of train where passengers are less than 50 \n8.Average number of passengers travelling in 12.04 train \n9.Diplay average number of passengers travelling in any train \n10.Enter 0 to stop");
	   System.out.println("Enter a number from menu");
	   menu=sc.nextInt();
	   switch(menu)
	   {
		   case 1:System.out.println("Day   Departuretime  passengernumber");
		   for(int i=0;i<=15;i++)
		   {
			   System.out.println(dt[i]+"\t\t\t\t"+pn[i]);
		   }
		   break;
		   case 2:for(int i=0;i<=15;i++)
		   {
			   if(pn[i]>190)
			   {
				   System.out.println(dt[i]);
			   }
		   }break;
		   case 3:for(int i=0;i<=15;i++)
		   {
			   if(pn[i]<15)
			   {
				   System.out.println(dt[i]);
			   }
		   }break;
		   case 4:if(pn[0]<pn[1]&&pn[5]<pn[6]&&pn[10]<pn[11])
		   {
			   System.out.println("9.04 train is popular tan 6.04 train");
		   }
		   else
		   {
			   System.out.println("6.04 train is popular tan 9.04 train");
		   }break;
		   case 5:if(pn[0]<pn[5])
		   {
			   System.out.println("6.04 train is on tuesday is more popular");
		   }
		   else if (pn[0]>pn[5])
			{
			    System.out.println("6.04 train is on monday is more popular");
		    }
			else
			{
				System.out.println("both train have same popularity");
			} break;
			case 6:List l=Arrays.asList(dt);
	        String s1,s2;
	        System.out.println("enter day and time of 2 train as(monday 6.04)");
	        s1=sc.nextLine();
	        s2=sc.nextLine();
	        int i,j;
	        i=l.indexOf(s1);
	        j=l.indexOf(s2);
	        System.out.println("passenger number in train1 :"+pn[i]+"\npassenger number in train 2 : "+pn[j]);
	        if(pn[i]>pn[j])
     	   {
		      System.out.println(s1+"train is more popular than " +s2+" train");
	       }
	       else if(pn[i]<pn[j])
	      {
		      System.out.println(s2+" train is more popular than " +s1+ "train"); 
    	   }
	       else
	     {
		      System.out.println("both train have same polularity");
	      }break;
		  case 7:for(int n=0;n<=15;n++)
	      {
			  if(pn[n]<50)
		          {
			         System.out.println(dt[n]+"\n");
		          }
	       }break;
		   case 8:int sum;
	       sum=(pn[2]+pn[7]+pn[12]);
	       System.out.println("Average number of passengers travelling in 12.04 train in 3 day "+(sum/3));
		   break;
		   case 9:System.out.println("enter the day and time of the train to display the average no. of passengers");
	       String s=sc.nextLine();
		   List k=Arrays.asList(dt);
	       int m=k.indexOf(s);
	       System.out.println("average number of passengers traveling in "+s+" train is "+pn[m]); 
		   break;
	   }
	}
}}
