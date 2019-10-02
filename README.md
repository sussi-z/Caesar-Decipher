# Caesar-Decipher
/*
e.g. enter text to decrypt: Yg wugf vq nqqm wr vq uma cpf yqpfgt cv qwt rnceg kp uvctu, pqy yg lwuv nqqm fqyp cpf yqtta cdqwv qwt rnceg kp vjg fktv.
	key=2
	Output: We used to look up to sky and wonder at our place in stars, now we just look down and worry about our place in the dirt.	
*/

#include <stdio.h>
#include <string.h>
#include <conio.h>
int main()
{	
	int i=0,key;
	char n[1000];
	printf("enter text to decrypt:\n");
	gets(n);
	printf("enter the key:\n");
	scanf("%d",&key);
	
	while(n[i]!='\0')
  	{
		if(!((n[i]>=0&&n[i]<65)||(n[i]>90&&n[i]<97)||(n[i]>122&&n[i]<=127)))
 			{
				int a=0;
				a+=(96<n[i]<123?((n[i]-97-key)%26+97):((n[i]-65-key)%26+65));
				
				if(n[i]>='A'&&n[i]<='Z' && a>90)
				{
					a-=90;
					a+=64;
				}
				
				if(n[i]>='a'&&n[i]<='z' && a<97)
				{
					a=97-a;
					a=123-a;
				}
				
				printf("%c",a);
 			}
 		else
 			{
 				printf("%c",n[i]);
 			}
	i++;
	}
}
