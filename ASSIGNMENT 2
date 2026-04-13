#include<stdio.h>
#include<stdlib.h>
#include<unistd.h>
#include<sys/types.h>
#include<sys/wait.h>
#include<fcntl.h>
#include<string.h>
int main(){
char texts[100];
    int fd;
    fd = open("data.txt",O_CREAT|O_WRONLY|O_TRUNC,0644);
    printf("Enter text to write into file\n");
    fgets(texts,sizeof(texts),stdin);
    write(fd,texts,strlen(texts));
   if(fd<0){
    perror("file not opened");
    exit(1);
   }

    pid_t pid = fork();

    // parent logic

    if(pid==0){

        read(fd,texts,sizeof(texts));
        printf("%s",texts);
        close(fd);
        exit(0);

        }else{
            sleep(1);
            // (fd,texts,sizeof(texts));
            write(fd,texts,sizeof(texts));
        }

return 0;

}
