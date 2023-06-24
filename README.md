# Decimal-to-Hexadecimal-Conversion-in-C

Decimal to Hexadecimal Conversion in C
Here, in this section, we will discuss the Decimal to Hexadecimal conversion in C.

Hexadecimal are base 16 numbersystem. This system,, has numerals 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, and 15

The double digit numerals are represented with alphabets 10 : A, 11 : B, 12 : C, 13 : D, 14 : E, 15 : F

Decimal to Hexadecimal Conversion in C
Method
To know how to solve this you must first have knowledge of ASCII Table. The program works in two cases
If the current remainder left >= 10
Must be replaced by (A – F)
Else if current remainder < 10
Must be replaced by (0- 9)
Decimal to HexaDecimal in C Program
Related Pages
Decimal to Binary conversion

Decimal to Octal Conversion

Decimal to Hexadecimal Conversion

Binary to Octal conversion

Octal to Binary conversion

Quadrants in which a given coordinate lies

Code in C
Run
#include<stdio.h>

void convert (int num)
{
  // creating a char array to store hexadecimal equivalent
  char hexa[100];

  // using i to store hexadecimal bit at given array position
  int i = 0;
  while (num != 0)
    {
      int rem = 0;


      rem = num % 16;

      // check if rem < 10 : Digits : 0 - 9
      // ascii 0 : 48
      if (rem < 10) { hexa[i] = rem + 48; i++; } 
// else positional values : A - F 
// rem value will be > 10, adding 55 will result : A - F 
// ascii A : 65, B : 66 ..... F : 70 
      else
	{
	  hexa[i] = rem + 55;
	  i++;
	}
      num = num / 16;
    }
// printing hexadecimal array in reverse order
printf ("Hexadecimal:");
  for (int j = i- 1; j >= 0; j--)
    printf ("%c" , hexa[j]);
}

int main ()
{
  int decimal = 1457;
  convert (decimal);
  return 0;
}
Output
Hexadecimal: 5B1
