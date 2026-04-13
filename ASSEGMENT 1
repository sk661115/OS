# include < stdio .h >
# include < stdlib .h >
# include < unistd .h >
# include < sys / wait .h >
# include < time .h >
int main () {
int arr [30] , key1 , key2 , status ;
pid_t p1 , p2 ;
srand ( time ( NULL ) ) ;
printf (" Array : ") ;
for (int i = 0; i < 30; i ++) {
arr [ i ] = rand () % 50 + 1;
printf ("%d ", arr [ i ]) ;
}
printf ("\n\ nEnter Key 1 and Key 2: ") ;
scanf ("%d %d", & key1 , & key2 ) ;
// Child 1
p1 = fork () ;
if (p1==0) {
  for(int j = 0; j < 15 ; j++){
    if(arr[j]==key1){
      exit(j);
    }
  }exit(255);
}
// Parent waits for Child 1
waitpid ( p1 , & status , 0) ;
int res1 = WEXITSTATUS ( status ) ;

  if(res1 == 255){
    printf("Key1 not found");
  }else{
    printf("Key1 Found");
  }
// Child 2
p2 = fork () ;
if (p2==0) {
  for(int j = 0; j < 15 ; j++){
    if(arr[j]==key2){
      exit(j);
    }
  }exit(255);
}

// Parent waits for Child 2
waitpid ( p2 , & status , 0) ;
int res2 = WEXITSTATUS ( status ) ;
 if(res2 == 255){
    printf("Key2 not found");
  }else{
    printf("Key2 Found");
  }
return 0;
}
