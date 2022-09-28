- 👋 Hi, I’m @18300891017
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
18300891017/18300891017 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
#include"stdio.h"
#include"malloc.h"
#define maxsize 1024
typedef char datatype;
typedef struct
{
	datatype data[maxsize];
	int last;
}sequenlist;
int insert(sequenlist* L, datatype x, int i)
	{
		int j;
		if (L->last == maxsize - 1)
		{
			printf("overflow");
			return 0;
		}
		else if ((i < 0) || (i > L->last))
		{
			printf("error,please input the right 'i'");
			return 0;
		}
		else
		{
			for (j = L->last; j >= i; j--)
				L->data[i] = L->data[i + 1];
			L->data[i] = x;
			L->last = L->last + 1;
		}
		return(1);
	}
	int dellist1(sequenlist* L, int i)
	{
		if ((i < 0) || i > L->last,i++)
{
     printf("error,please input the right i");
	 return 0;
}
		else
		{
			int j;
			int x;
			printf("%d",&x);
			
			for (j = L->last; j >= i; j--)
				L->data[j + 1] = L->data[j];
			L->data[i] = x;
			L->last = L->last + 1;
		}
		return(1);
	}
	int dellist2(sequenlist* L, int i)
	{
		if ((i < 0) || (i > L->last))
		{
			printf("error,please input the right i");
				return 0;
		}
		else
		{
			for (i;i<L->last; i++)
				L->data[i] =L->data[i+1];
			L->last = L->last -1;
			return(1);
		}
	}
	void creatlist(sequenlist* L)
	{
		int n, i;
		char tmp;
		printf("请输入数据的个数:\n");
		scanf("%d", &n);
		for (i = 0; i < n; i++)
		{
			printf("data[%d]=",i);
			fflush(stdin);
			scanf("%c", &tmp);
		}
		L->last = n - 1;
		printf("%n",&n-1);
	}
	void printout(sequenlist* L)
	{
		int i;
		for (i = 0; i <= L->last; i++)
		{
			printf("data[%d]=", i);
			printf("%c\n", L->data[i]);

		}
	}
	int main()
	 {
		sequenlist* L;
		char cmd,x;
		int i;
		L = (sequenlist*)malloc(sizeof(sequenlist));
		creatlist(L);
		printout(L);
		do
		{
			printf("i,I...插入\n");
			printf("d,D...插入\n");
			printf("q,Q...插入\n");
			do
			{
				fflush(stdin);
				scanf("%c",&cmd);
			} while( (cmd != 'd') && (cmd != 'D') && (cmd != 'q') && (cmd != 'Q') && (cmd != 'i') && (cmd != 'I'));
			switch (cmd)
			{
			case 'i':
			case 'I':
				printf("请输入你要插入的数据:");
				scanf("%d", &i);
				insert(L, x, i);
				printout(L);
				break;
			case'd':
			case'D':
				printf("请输入你要删除元素的位置：");
				fflush(stdin);
				scanf("%d", &i);
				dellist2(L, i);
				printout(L);
				break;
			}
		} while ((cmd != 'q') && (cmd != 'Q'));
	}
