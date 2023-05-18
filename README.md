# c-p72-3-
c语言学习笔记p72 文件操作（3）
  #include<stdio.h>
  #include<errno.h>
  #include<string.h>
  int main()
  {
        FILE* pf=fopen("test.txt","w");
        if(pf==NULL)
        {
              printf("%s\n",strerro(errno));
              return 0;
        }
        //写文件
        fputc('b',pf);
        fputc('i',pf);
        fputc('t',pf);
        //读文件
        int c=fgetc(pf);
        printf("%c",ch);//输出b
        ch=fgetc(pf);//字符输入函数
        printf("%c",ch);//输出i
        //关闭文件
        fclose(pf);
        pf=NULL;
        return 0;
  }



int main()
{
      char buf[1024]={0};
      FILE* pf=fopen("test,txt","r");
      if(pf==NULL)
      {
            return 0;
      }
      //读文件
      fgets(buf,1024,pf);
      printf("%s\n",buf);//这里面的buf自带一个换行，输出bit
      41行可以用puts（buf);替代，这里的puts自带换行和buf连用空两行
      
     //关闭文件
     fclose(pf);
     pf=NULL;
      return 0;
}



int main()
{
      char buf[1024]={0};
      FILE* pf=fopen("test,txt","w");
      if(pf==NULL)
      {
            return 0;
      }
      //写文件
      fputs("hello",pf);
      fputs("world",pf);//这里不会换行，因此需要自己加
     //关闭文件
     fclose(pf);
     pf=NULL;
      return 0;
}


int main()
{
      //从键盘读取一行文本消息
      char buf[1024]={0};
      fgets(buf,1024,stdin);//文本行输入函数，从标准输入读取
      fputs(buf,stdout);//输出到标准输出流
      //74，75行的代码等价于
      gets(buf);
      puts(buf);
      return 0;
}


struct S
{
      int n;
      float score;
      char arr[10];
};
int main()
{
      struct S s={100;3.14f,"biit"};
      FILE* pf=fopen("test.txt","w");
      if(pf==NULL)
      {
            return 0;
      }
      //格式化的形式写文件
      fprintf(pf,"%d %f %s",s.n,s.score,s.arr);
      //关闭文件
      fclose (pf);
      pf=NULL;
      return 0;
}


struct S
{
      int n;
      float score;
      char arr[10];
};
int main()
{
      struct S s={0};
      FILE* pf=fopen("test.txt","r");
      if(pf==NULL)
      {
            return 0;
      }
      //格式化的形式输入数据
      fscanf("%d %f %s",&(s.n),&(s.score),s.arr);
      printf("%d %f %s\n",s.n, s.score,s.arr);
      //关闭文件
      fclose (pf);
      pf=NULL;
      return 0;
}


struct S
{
      int n;
      float score;
      char arr[10];
};
int main()
{
      struct S s={0};
     fscanf(stdin,"%d %f %s",&(s.n),&(s.score),s.arr);
     fprintf(stdout,"%d %f %s",s.n, s.score, s.arr);
      return 0;
}


scanf/printf 是针对标准输入流/标准输出流的格式化输入/输出语句
fscanf/fprintf 是针对所有输入流/所有输出流的格式化输入/输出语句。  包含第一种
sscanf/sprintf sscanf是从字符串中读取格式化的数据/sprintf是把格式化数据输出成（存储到）字符串


struct S
{
      int n;
      float score;
      char arr[10];
};
int main()
{
      struct S s={100,3.14f,"abcdef"};
      struct S tmp={0};
      char buf[1024]={0};
      //把格式化的数据存转化为字符串存储到buf
      sprintf(buf,"%d %f %s",s.n, s.score, s.arr);
      printf("%s\n",buf);//这里的输出和fprintf一样，但是这里的结果已经转化为字符串
      //从buf中读取格式化的数据到tmp中
      sscanf(buf,"%d %f %s",&(tmp.n),&(tmp.score),tmp.arr);
      printf("%d %f %s\n",tmp.n, tmp.score, tmp.arr);//把格式化的
      
      return 0;
}





