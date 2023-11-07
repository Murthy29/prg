
 
fake(()
import java.util.Scanner;
public class greed
{
public static void main(String args[])
{
int n,i,j=0,m;
float max,rc=0,pr=0,x;
int p[]=new int[50];
int w[]=new int[50];
Scanner sc=new Scanner(System.in);
System.out.println("enter a obj");
n=sc.nextInt();
System.out.println("enter a weight of each object");
for(i=1;i<=n;i++)
w[i]=sc.nextInt();
System.out.println("enter a prof of each object");
for(i=1;i<=n;i++)
p[i]=sc.nextInt();
System.out.println("enter a max capacity of knap");
m=sc.nextInt();
rc=m;
while(rc>0)
{
max=0;
for(i=1;i<=n;i++)
{
if(((float)p[i])/((float)w[i])>max)
{
max=((float)p[i])/((float)w[i]);
j=i;
}
}
if(w[j]<=rc)
{
System.out.println("ob number:"+j+" of weight added is:"+w[j]);
pr=pr+p[j];
rc=rc-w[j];
p[j]=0;
}
else
{
System.out.println("ob number:"+j+" of weight added is:"+rc);
x=rc/w[j];
pr=pr+(p[j]*x);
rc=0;
}
}
System.out.println("the toptal profit is:"+pr);
sc.close();
}
}


knap(dynamic approche)
import java.util.scanner;
public class ksmanu
{
	public static int v[][]=new int[15][15];
	public void knapsackDP(int n,int m,int w[],int p[])
	{
		int i,j;
		for(i=0;i<=n;i++)
		{
			for(j=0;j<=m;j++)
			{
				if(i==0||j==0)
				   v[i][j]=0;
				else if(w[i]>j)
				   v[i][j]=v[i-1][j];
				else
				{
					if(v[i-1][j]<(v[i-1][j-w[i]]+p[i]))
						v[i][j]=v[i-1][j-w[i]]+p[i];
					else
					   v[i][j]=v[i-1][j];
				}
			}
		}
	system.out.println("\n profit table");
	for(i=0;i<=n;i++)
	{
		for(j=0;j<=m;j++)
		{
			system.out.print(v[i][j]+ "\t");
		}
		system.out.print("\n")
	}
	system.out.println("\n the optimal solution is"+v[n][m]);
	}
	public void object selection(int n,int m,int w[],int v[][])
	{
		int x[]=new int[n+1];
		int i,j;
		for(i=1;i<=n;i++)
		  x[i]=0;
		i=n;j=m;
		while(i>0&&j>0)
		{
			if(v[i][j]!=v[i-1][j])
			{
				x[i]=1;
				j=j-w[i];
			}
				i--;
		}
	system.out.println("\n objects selected are:");
	for(i=1;i<=n;i++)
	if(x[i]==1)
		system.out.println("object"+ i);
	}
public static void main(string args[])
{
	int w[]=new int[10];
	int p[]=new int[10];
	scanner sc=new scanner(system.in);
system.out.println("enter the number of objects");
int n=sc.nextInt();

system.out.println("\n enter weight for"+n" object");
for(int i=1;i<=n;i++)
w[i]=sc.nextInt();


system.out.println("\n enter profit for"+n" object");
for(int i=1;i<=n;i++)
p[i]=sc.nextInt();

system.out.println("enter the capacity of the bag");
int m=sc.nextInt();

ksmanu obj=new ksmanu1();
obj.knapsackDP(n,m,w,p);
obj.objectselection(n,m,w,v);
sc.class();
}
}




