<div align="center">

## Statistical  Lab


</div>

### Description

Hi there ;

Today I am here with you with my new code name "STATLAB". Actually I made this for those who work in "Probability And Statistics". These funtionalities are often not found in any Scientific calculators. So Go ahead use it  , I made it free of cost for my beloved fellows.
 
### More Info
 
AS PER SELECTION.

AS YOU WANT.

Not at all man. Really Cool.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Syed  Umair  Ali  Shah](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/syed-umair-ali-shah.md)
**Level**          |Intermediate
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |C, C\+\+ \(general\), Borland C\+\+
**Category**       |[Complete Applications](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/complete-applications__3-7.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/syed-umair-ali-shah-statistical-lab__3-2534/archive/master.zip)

### API Declarations

```
#include<iostream.h>
#include<conio.h>
#include<math.h>
#include<stdlib.h>
```


### Source Code

```
//////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
/////						  			 /////
/////                  /////
/////      STAT LAB                             /////
/////		   				     /////
/////									 /////
//////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
#include<iostream.h>
#include<conio.h>
#include<math.h>
#include<stdlib.h>
const int len = 200;
const float e = 2.718281828;
enum boolean {true ,false};
class dis_cal
 {
 public:
	dis_cal(); 				//initializes the values of dis_cal class
	void dis_menu();			//discriptive menu
	void dis_serial();           //discriptive menu details
	float dis_men(float a[], int size);   //calculates mean
	void dis_menshow();      		//shows mean
	float dis_med(float a[], int size);   //calculates & shows median
	void dis_mod(float a[], int size);   //calculates & shows mode
	float dis_rag(float a[], int size);   //calculates & shows range
	float dis_var(float a[], int size);   //calculates variance
	void dis_varshow(float variance);    //shows variance
	float dis_std();            //calculates & shows standard deviation
	void dis_quitin();           //quits from discriptve menu
	void in_menu(); 			//menu for data entry
	void in_serial();  			//input menu details
	void in_insert();   			//insert data
	void in_append();			//append data
	void in_delete();    		//delete data
	void in_remove();			//remove data
	void in_deleteall();  			//deletes all data in array
	void in_display();   			//displays the list
	void in_sort(); 			//sorts the array of data
	void in_calculations();			//goto discriptive stats class
	void in_checksize();          //checks whether the array size is ok or not
	void in_quit();	  			//quits from the input menu
	void charcheck(char[],boolean);
	void loccheck(char[],boolean);
	void locfrac(char[],boolean);
 protected:
	boolean locst;
	float mean;               //mean variable
	float mode;               //mode variable
	float median;              //median variable
	float range;              //range variable
	float variance;             //variance variable
	float standard;             //standard deviation variable
	int dis_srno;              //serial number variable for discriptive menu
	float a[len];	  			//data array
	int size;  	  			//size of data
	int in_srno;     			//serial number variable for input menu
	char memlist[2];  			//for conversion from ascii to float
 };
void dis_cal::loccheck(char temp[],boolean locst)
 {
 boolean locflag;
 locflag=false;
 long a=0;
 for (int i=0; temp[i]!='\0';i++)
  {
  a=temp[i];
  if(locflag)
   {
   if (a<46||a>57||a==47)
    {
	locflag=true;
	cout<<"\n**ERROR**\nPlease donot enter a character.";
	if (locst==0)
		in_delete();
	else
		in_remove();
    }
  else
	locflag=false;
   } //endif
  }//endfor
 }
void dis_cal:: locfrac(char temp[], boolean lcst)
 {
 for ( int i=0; temp[i]!='\0'; i++ )
  {
  if ( temp[i] == '.' )
   {
   cout<<"**ERROR**";
   cout<<"\nYour numbers should not be a fraction.";
   cout<<"\nEnter the values again.\n ";
   if (lcst==1)
	in_remove();
   else
	in_delete();
   }
  }
 }
void dis_cal::dis_cal()
 {
 mean 		= 0;
 mode 	= 0;
 median	= 0;
 range		= 0;
 variance	= 0;
 standard   = 0;
 size 		= 0;
 in_srno 	= 0;
 for ( int i=0; i<len; i++)
	a[i] = 0;
 for ( i=0; i<2; i++ )
	memlist[i] = ' ';
 }
void dis_cal::charcheck(char temp[], boolean locst)
{
 long a=0;
 boolean checkflag;
 checkflag=false;
 for (int i=0; temp[i]!='\0';i++)
 {
  a=temp[i];
  if(checkflag==1)
  {
   if(a!=42)
   {
    if (a<46||a>57||a==47)
	{
	 checkflag=true;
	 cout<<"\n*ERROR**\nPLease donot enter character values";
	 cout<<"\nEnter the values again";
	 if (locst==0)
		in_insert();
	 else
		in_remove();
	}
   }
   else
	checkflag=false;
  }//endif
 }//endfor
 }
void dis_cal::in_menu()
 {
 clrscr();
 cout<<"\n\tINPUT MENU\n\n";
 cout<<"1. Insert\n";
 cout<<"2. Delete\n";
 cout<<"3. Romove\n";
 cout<<"4. Empty List\n";
 cout<<"5. Display List\n";
 cout<<"6. Perform Calculations\n";
 cout<<"7. Go to Main Menu\n";
 }
void dis_cal::in_serial()
 {
 in_menu();
 in_srno = 0;
 while (in_srno != '7')
  {
  cout<<"\n\nEnter your choice from 1-7 from the input menu : ";
  in_srno = getche();
  cout<<"\n";
  switch(in_srno)
   {
   case '1':		in_insert();		break;
   case '2':  	in_delete();     	break;
   case '3':  	in_remove();    	break;
   case '4':  	in_deleteall();  	break;
   case '5':  	in_display();   	break;
   case '6':  	in_checksize();     break;
   case '7':  	in_quit();    	break;
   default:
   cout<<"\n\t**ERROR 1-7 only allowed**";
   }//end switch
  cout<<"\n";
  in_menu();
  }//end while
 }
void dis_cal::in_insert()
 {
 locst=true;
 *memlist = '\0';
 int temp=0;
 size = 0;
 cout<<"\n\t*INSERT ELEMENT*\n";
 cout<<"\nEnter the array of data ";
 cout<<"\nWhen you are done type * to exit array entry\n\n";
 do
  {
  cout<<"Enter the element "<<size+1<<" of array : ";
  cin>>memlist;
  temp=size++;
  a[temp] = atof(memlist);
  charcheck(memlist,locst);
  }
 while ( *memlist != '*' );
 if (a[temp]==0)
  {
  size--;
  cout<<"\nPress any key to continue....";
  getch();
  }
 }
void dis_cal::in_delete()
 {
 locst=true;
 int i, location=0;
 cout<<"\n\t*DELETE ITEM*\n";
 if ( size != 0 )
  {
  cout<<"\nEnter the location whose element you want to delete : ";
  cin>>location;
  if ( location <= size )
   {
   location--;
   while ( location <= size )
    {
	a[location] = a[location+1];
	location++;
    }
   cout<<"\nElement deleted successfully";
   cout<<"\nPress any key to continue....";
   getch();
   }
  else
   {
   cout<<"\n**ERROR**\n The location must be less than or equal to "<<size<<"\n\tRepeat the above process again.";
   getch();
   in_delete();
   }
  }
 else
  {
  cout<<"\n**ERROR** \nThere must be some data in the list to perform this function";
  getch();
  }
 }
void dis_cal::in_remove()
 {
 locst=false;
 char dloc[30];
 int i,element,location=0;
 cout<<"\n\t*REMOVE ITEM*\n";
 if ( size != 0 )
  {
  cout<<"\nEnter the new element : ";
  cin>>memlist;
  charcheck(memlist,locst);
  cout<<"\nEnter the location whose element you want to replace : ";
  cin>>dloc;
  loccheck(dloc,locst);
  locfrac(dloc,locst);
  location=atoi(dloc);
  if ( location <= size )
   {
   a[location] = atof(memlist);
   cout<<"\nPress any key to continue....";
   getch();
   }
  else
   {
   cout<<"\n**ERROR**\n The location must be less than or equal to "<<size<<"\n\tRepeat the above process again.";
   getch();
   in_remove();
   }
  }
 else
  {
  cout<<"\n**ERROR**\n There must be some data in the list to perform this function";
  getch();
  }
 }
void dis_cal::in_deleteall()
 {
 int i;
 cout<<"\n\t*EMPTY LIST*\n";
 if ( size == 0 )
    cout<<"\nList is already empty";
 else
  {
  for (i=0; i<size; i++)
	a[i] = 0;
  cout<<"\nList is empty now";
  size = 0;
  }
 cout<<"\nPress any key to continue...";
 getch();
 }
void dis_cal::in_display()
 {
 int i;
 cout<<"\n\t*DISPLAY LIST*\n";
 for (i=0; i<size; i++)
	cout<<"\n "<<a[i];
 cout<<"\n\nPress any key to continue....";
 getch();
 }
void dis_cal::in_sort()
 {
 int out,in,temp;
 for ( out=0; out<size-1; out++ )
  {
  for ( in=out+1; in<size; in++ )
	if ( a[out] > a[in] )
	 {
	 temp = a[in];
	 a[in] = a[out];
	 a[out] = temp;
	 }
  }
 }
void dis_cal::in_checksize()
 {
 in_sort();
 if ( size < 2 )
  {
  cout<<"\n**ERROR**\nAs there is not enough data in the data list.";
  cout<<"\nYou cannot performs calculations now.";
  cout<<"\nEnter more data to perform calculations.";
  getch();
  }
 else
	dis_cal::dis_serial();
 }
void dis_cal::in_quit()
 {
 char sure;
 cout<<"\n\nAre you sure you want to quit from Input Menu.";
 cout<<"\n\nPress 'y' for yes or 'n' for no. : ";
 sure = getche();
 if ( sure == 'y' )
  {
  cout<<"\n\nQuiting from Input menu\n";
  cout<<"\n\t\t\t\t\t\tPress any key to continue.......";
  getch();
  }
 else
	in_serial();
 }
void dis_cal::dis_menu()
 {
 cout<<"\n\tDESCRIPTIVE STATS CALCULATION MENU\n\n";
 cout<<"1. Mean\n";
 cout<<"2. Median\n";
 cout<<"3. Mode\n";
 cout<<"4. Range\n";
 cout<<"5. Variance\n";
 cout<<"6. Standard Deviation\n";
 cout<<"7. Quit Discriptive Stats Menu\n";
 }
void dis_cal::dis_serial()
 {
 clrscr();
 dis_menu();
 dis_srno = 0;
 while (dis_srno != '7')
  {
  cout<<"\n\nEnter your choice from 1-7 from the menu : ";
  dis_srno = getche();
  cout<<"\n";
  switch(dis_srno)
   {
   case '1':		dis_menshow();			break;
   case '2':		dis_med(a,size);		break;
   case '3':  	dis_mod(a,size);    	break;
   case '4':     dis_rag(a,size);		break;
   case '5':  	dis_varshow(variance); 	break;
   case '6': 	dis_std();			break;
   case '7':  	dis_quitin();      	break;
   default:
   cout<<"\n\t**ERROR 1-7 only allowed**";
   cout<<"\n\n\tPress any key to continue...";
   getche();
   }//end switch
  cout<<"\n";
  clrscr();
  dis_menu();
  }//end while
 }
float dis_cal::dis_men(float a[], int size)
 {
 mean = 0.0;
 for ( int i = 0; i < size; i++ )
	mean += a[i];
 mean = mean / size;
 return mean;
 }
void dis_cal::dis_menshow()
 {
 cout<<"\n\nMean \xE6 : "<<dis_men(a, size);
 cout<<"\n\nPress any key to continue...";
 getche();
 }
float dis_cal::dis_med(float a[], int size)
 {
 median = 0.0;
 for ( int i = 0; i < size; i++ )
  {
  if ( size % 2 == 0 )
   {
   median = a[(size/2)-1] + a[((size+2)/2)-1];
   median = median / 2;
   }
  else
	median = a[((size+1)/2)-1];
  }
 cout<<"\n\nMedian : "<<median;
 cout<<"\n\nPress any key to continue...";
 getche();
 return median;
 }
void dis_cal::dis_mod(float a[], int size)
 {
 cout<<"\n";
 for ( int i = 0; i < size; i++ )
  {
  for ( int j = 0; j < size; j++ )
   {
   if ( a[i] == a[j] )
	mode++;
   }
  cout<<"\nElement "<<i<<" i.e., "<<a[i]<<" occurs "<<mode<<" times";
  mode = 0;
  }
 cout<<"\n\nPress any key to continue...";
 getche();
 }
float dis_cal::dis_rag(float a[], int size)
 {
 range = 0.0;
 range = a[size-1] - a[0];
 cout<<"\n\nRange : "<<range;
 cout<<"\n\nPress any key to continue...";
 getche();
 return range;
 }
float dis_cal::dis_var(float a[], int size)
 {
 float numerator = 0.0;
 variance = 0.0;
 dis_men(a, size);
 for ( int i = 0; i < size; i++ )
	numerator += ( a[i] - mean ) * ( a[i] - mean );
 variance = numerator / size;
 return variance;
 }
void dis_cal::dis_varshow(float variance)
 {
 cout<<"\n\nVariance \xE5\xFD : "<<dis_var(a, size);
 cout<<"\n\nPress any key to continue...";
 standard = sqrt(variance);
 getche();
 }
float dis_cal::dis_std()
 {
 dis_var(a, size);
 standard = sqrt(variance);
 cout<<"\n\nStandard Deviation \xE5 : "<<standard;
 cout<<"\n\nPress any key to continue...";
 getche();
 return standard;
 }
void dis_cal::dis_quitin()
 {
 char sure;
 cout<<"\n\nAre you sure you want to quit from Discriptive Stats Menu.";
 cout<<"\n\nPress 'y' for yes or 'n' for no. : ";
 sure = getche();
 if ( sure == 'y' )
  {
  cout<<"\n\nQuiting from Discriptive Stats Menu\n";
  cout<<"\n\t\t\t\t\t\tPress any key to continue.......";
  getch();
  }
 else
	dis_serial();
 }
//////////////////////////////////////////////////////////////////////////////
class binomial
 {
 private:
	char dy[50];
	char dn[50];
	char dp[50];
	float p;			 	//probability of success on a single a trial
	float prob;			 	//probability distribution of binomial
	float var; 				//variance
	float mean;               //mean
	int y;				 	//number of successes
	int n;     			 	//number of trials
	boolean binst;
 public:
	binomial():n(0),y(0),p(0.0),prob(0.0),var(0.0),mean(0.0)
		{ }
	void biin_p();			 	//input function for p
	void biin_ny();			 	//input function for n & y
	void bi_cal(); 	    	 	//caculates the binomial distribution & variance & mean
	void bi_show();				//shows probability & variance & mean
	void bi_complete();        	//prerforms complete operation
	friend float power(float, float); 	//calculates power
	friend double fact(int);	 	//calculates factorial
	void binfrac(char[]);
	void binchar(char[],boolean);
 };
void binomial::binchar(char temp[],boolean)
 {
 boolean binflag;
 binflag=false;
 long a=0;
 for (int i=0; temp[i]!='\0';i++)
  {
  a=temp[i];
  if(binflag==1)
   {
   if (a<46||a>57||a==47)
    {
	binflag = true;
	cout<<"\n**ERROR**\nPlease donot enter a character";
	if (binst)
		biin_ny();
	else
		biin_p();
    }
   else
	binflag = false;
   } //endif
  }//endfor
 }
void binomial:: binfrac(char temp[])
 {
 for ( int i=0; temp[i]!='\0'; i++ )
  {
  if ( temp[i] == '.' )
   {
   cout<<"**ERROR**";
   cout<<"\nYour numbers should not be a fraction.";
   cout<<"\nEnter the values again.\n ";
   biin_ny();
   }
  }
 }
void binomial::biin_p()
 {
 binst=true;
 cout<<"\nEnter probability of success on a single a trial (p): "; cin>>dp;
 binchar(dp,binst);
 p=atof(dp);
 if ( p > 1 || p < 0 )
  {
  cout<<"\n**ERROR**";
  cout<<"\nThe probabilty must be less than 1 and greater than 0.";
  cout<<"\nEnter the probability again.\n";
  biin_p();
  }
 }
void binomial::biin_ny()
 {
 binst=false;
 cout<<"\nEnter the number of trials : "; cin>>dn;
 cout<<"\nEnter the number of successes : "; cin>>dy;
 binfrac(dn);
 binchar(dn,binst);
 binfrac(dy);
 binchar(dy,binst);
 n = atoi(dn);
 y = atoi(dy);
 if ( n < y )
  {
  cout<<"\n**ERROR**";
  cout<<"\nMan this is not possible.";
  cout<<"\nNumber of trials can never be less than number of successes.";
  cout<<"\nEnter the number of trials and successes again.\n";
  biin_ny();
  }
 }
void binomial::bi_cal()
 {
 float q = 0.0;				//probability of faliure
 q = 1.0 - p;
 prob = ( fact(n) / ( fact(y)*fact(n-y) ) ) * (power(p,y) * power((1-p),(n-y)));
 var = n * p * q;
 mean = n * p;
 }
void binomial::bi_show()
 {
 cout<<"\n\nThe Probability of the binomial distribution p(y) is : "<<prob;
 cout<<"\n\nThe Variance of Binomial Distribution \xE5\xFD is : "<<var;
 cout<<"\n\nThe Mean of Binomial Distribution \xE6 is : "<<mean;
 cout<<"\n\nPress any key to go to DRV Menu ...";
 }
void binomial::bi_complete()
 {
 clrscr();
 cout<<"\n\t\t\tBINOMIAL DISTRIBUTION:\n";
 biin_p();
 biin_ny();
 bi_cal();
 bi_show();
 binomial();
 getch();
 }
//////////////////////////////////////////////////////////////////////////////
class negative
 {
 private:
	boolean negst;
	char dp[50];
	char dr[50];
	char dy[50];
	float p;			 	//probability of success on a single a trial
	float prob;			 	//probability distribution of negative
	float var; 				//variance
	float mean;               //mean
	int r;     			 	//success point
	int y;				 	//number of successes until success point is observed
 public:
	negative():r(0),y(0),p(0.0),prob(0.0),mean(0.0),var(0.0)
		{ }
	void negin_p();			 	//input function for p
	void negin_ry();		 	//input function for r & y
	void geomatric_check();		 	//geomatric distribution "special case"
	float neg_cal();     	 	//caculates the negative binomial distribution & variance & mean
	void neg_show();		 	//shows the the negative binomial distribution & variance & mean
	void neg_complete();		 	//prerforms complete operation
	friend float power(float, float); 	//calculates power
	friend double fact(int);	 	//calculates factorial
	void negfrac(char[]);
	void negchar(char[],boolean);
 };
void negative::negchar(char temp[],boolean)
 {
 boolean negflag;
 negflag=false;
 long a=0;
 for (int i=0; temp[i]!='\0';i++)
  {
  a=temp[i];
  if(negflag==1)
   {
   if (a<46||a>57||a==47)
    {
	negflag=true;
	cout<<"\n**ERROR**\nPlease donot enter a character";
	if (negst)
		negin_ry();
	else
		negin_p();
    }
   else
	negflag=false;
   }//end if
  }//end for
 }
void negative:: negfrac(char temp[])
 {
 for ( int i=0; temp[i]!='\0'; i++ )
  {
  if ( temp[i] == '.' )
   {
   cout<<"**ERROR**";
   cout<<"\nYour numbers should not be a fraction.";
   cout<<"\nEnter the values again.\n ";
   negin_ry();
   }
  }
 }
void negative::negin_p()
 {
 negst=true;
 cout<<"\nEnter probability of success on a single a trial (p) : "; cin>>dp;
 negchar(dp,negst);
 p=atof(dp);
 if ( p > 1 || p <= 0 )
  {
  cout<<"\n**ERROR**";
  cout<<"\nThe probabilty must be less than 1 and greater than 0.";
  cout<<"\nEnter the probability again\n";
  negin_p();
  }
 }
void negative::negin_ry()
 {
 negst=false;
 cout<<"\nEnter the success point (r) : "; cin>>dr;
 cout<<"\nEnter the number of trials until success is observed : "; cin>>dy;
 negfrac(dr);
 negchar(dr,negst);
 r=atoi(dr);
 negfrac(dy);
 negchar(dy,negst);
 y=atoi(dy);
 if ( y < 0 || r < 0 )
  {
  cout<<"\n**ERROR**";
  cout<<"\nNegative numbers are not allowed.";
  cout<<"\nEnter the numbers again.\n";
  negin_ry();
  }
 if ( y < r )
  {
  cout<<"\n**ERROR**";
  cout<<"\nMan this is not possible.";
  cout<<"\nNumber of trials can never be less than success point.";
  cout<<"\nEnter the number of trials and successes again.\n";
  negin_ry();
  }
 geomatric_check();
 }
void negative::geomatric_check()
 {
 if ( r == 1 )
  {
  cout<<"\nHere r = 1;\nThis is a special case of Negative Binomial Distribution.";
  cout<<"\nThis case is called Geomatric Distribution. ";
  cout<<"\n\nThe answer of Geomatric Probability Distribution is : "<<neg_cal();
  }
 else
	neg_cal();
 }
float negative::neg_cal()
 {
 float q = 0.0;				//probability of faliure
 q = 1 - p;
 prob = ( fact(y-1) / ( fact(y-r)*fact(r-1) ) ) * (power(p,r) * power(q,(y-r)));
 var = ( r * q ) / ( (p*p) );
 mean = r / p;
 return prob;
 }
void negative::neg_show()
 {
 cout<<"\n\nThe Probability of the negative binomial distribution p(y) is : "<<prob;
 cout<<"\n\nThe Variance of the negative binomial distribution \xE5\xFD is : "<<var;
 cout<<"\n\nThe Mean the negative binomial distribution \xE6 is : "<<mean;
 cout<<"\n\nPress any key to go to DRV Menu ...";
 }
void negative::neg_complete()
 {
 clrscr();
 cout<<"\n\t\t\tNEGATIVE BINOMIAL DISTRIBUTION:\n";
 negin_p();
 negin_ry();
 neg_cal();
 neg_show();
 negative();
 getch();
 }
//////////////////////////////////////////////////////////////////////////////
class poisson
 {
 private:
	char dy[50];
	char dlemda[50];
	int y;     		     	//the number of times a particular event occurs
	float lemda;			 	//mean number of events during the given time period
	float var;				//variance
	float mean;				//mean
	float prob;			 	//the poisson probabilty distrtribution
 public:
	poisson():y(0),lemda(0.0),prob(0.0),mean(0.0),var(0.0)
		{ }
	void posin_lemy();		 	//input function for lemda & y
	void pos_cal();     	 	//caculates the poisson probability distribution & variance & mean
	void pos_show();	     	//shows the the poisson probability distribution & variance & mean
	float powr(float, float); 	 	//calculates power
	void pos_complete();          //prerforms complete operation
	friend double fact(int);	 	//calculates factorial
	void posfrac(char[]);
	void poschar(char[]);
 };
void poisson::poschar(char temp[])
 {
 boolean posflag;
 posflag=false;
 long a=0;
 for (int i=0; temp[i]!='\0';i++)
  {
  a=temp[i];
  if(posflag==1)
   {
   if (a<46||a>57||a==47)
    {
	posflag=true;
	cout<<"\n**ERROR**\nPlease donot enter a character";
	posin_lemy();
    }
   else
	posflag=false;
   } //end if
  }//end for
 }
void poisson:: posfrac(char temp[])
 {
 for ( int i=0; temp[i]!='\0'; i++ )
  {
  if ( temp[i] == '.' )
   {
   cout<<"**ERROR**";
   cout<<"\nYour numbers should not be a fraction.";
   cout<<"\nEnter the values again.\n ";
   posin_lemy();
   }
  }
 }
void poisson::posin_lemy()
 {
 cout<<"\nEnter the number of times a particular event occurs (y) : "; cin>>dy;
 cout<<"\nEnter the number of events during the given time period (lemda): "; cin>>dlemda;
 posfrac(dy);
 poschar(dy);
 poschar(dlemda);
 lemda=atof(dlemda);
 y=atoi(dy);
 if (y<0)
  {
  cout<<"Event cant be in negative because we dont have time machine\n";
  posin_lemy();
  }
 }
void poisson::pos_cal()
 {
 float lem = -1 * lemda;
 if ( lemda == 0 )
	prob = 0;
 else
	prob = ( pow(lemda,y) * pow(e,lem) ) / ( fact(y) );
 var = lemda;
 mean = lemda;
 }
void poisson::pos_show()
 {
 cout<<"\n\nThe Probability of the Poisson Distribution p(y) is : "<<prob;
 cout<<"\n\nThe Variance of the Poisson Distribution \xE5\xFD is : "<<var;
 cout<<"\n\nThe Mean of the Poisson Distribution \xE6 is : "<<mean;
 cout<<"\n\nPress any key to go to DRV Menu ...";
 }
void poisson::pos_complete()
 {
 clrscr();
 cout<<"\n\t\t\tPOISSON DISTRIBUTION:\n";
 posin_lemy();
 pos_cal();
 pos_show();
 poisson();
 getch();
 }
//////////////////////////////////////////////////////////////////////////////
class hyper
 {
 private:
	char dr[50];
	char dn[50];
	char dy[50];
	char dtotal[50];
	int total;			 	//total number of elements
	int r;				 	//number of successes in total elements
	int n;				 	//number of elements drawn
	int y;				 	//number of successes drawn in 'n' elements
	float var;               //variance
	float mean;				//mean
	float prob;			 	//probability of hyper distibution
 public:
	hyper():total(0),r(0),n(0),y(0),prob(0.0),mean(0.0),var(0.0)
		{ }
	void hyp_in();		 	 	//input function for total, n, r, y
	void hyp_checkin();		 	//checks if input is valid
	void hyp_cal();     	 	//caculates the hypergeomatric distribution & variance & mean
	void hyp_show();			//shows the hypergeomatric distribution & variance & mean
	void hyp_complete();			//prerforms complete operation
	friend float power(float, float); 	//calculates power
	friend double fact(int);	 	//calculates factorial
	void hypchar(char[]);
	void hypfrac(char[]);
 };
void hyper:: hypfrac(char temp[])
 {
 for ( int i=0; temp[i]!='\0'; i++ )
  {
  if ( temp[i] == '.' )
   {
   cout<<"**ERROR**";
   cout<<"\nYour numbers should not be a fraction.";
   cout<<"\nEnter the values again.\n ";
   hyp_in();
   }
  }
 }
void hyper::hypchar(char temp[])
 {
 boolean hypflag;
 hypflag=false;
 long a=0;
 for (int i=0; temp[i]!='\0';i++)
  {
  a=temp[i];
  if(hypflag==1)
   {
   if (a<46||a>57||a==47)
    {
	hypflag=true;
	cout<<"\n**ERROR**\nPlease donot enter a character";
	hyp_in();
    }
   else
	hypflag=false;
   } //endif
  }//endfor
 }
void hyper::hyp_in()
 {
 cout<<"\nEnter the total number of elements (N) : "; cin>>dtotal;
 cout<<"\nEnter the number of elements drawn (n) : "; cin>>dn;
 cout<<"\nEnter number of successes in the total number of elements (r) : "; cin>>dr;
 cout<<"\nEnter the number of successes drawn, in number of elements drawn (y) : "; cin>>dy;
 hypchar(dtotal);
 hypfrac(dtotal);
 total=atoi(dtotal);
 hypchar(dn);
 hypfrac(dn);
 n=atoi(dn);
 hypchar(dr);
 hypfrac(dr);
 r=atoi(dr);
 hypchar(dy);
 hypfrac(dy);
 y=atoi(dy);
 hyp_checkin();
 }
void hyper::hyp_checkin()
 {
 if ( total < 0 || n < 0 || r < 0 || y < 0 )
  {
  cout<<"\n**ERROR**";
  cout<<"\nNegative numbers are not allowed.";
  cout<<"\nEnter the numbers again.\n";
  hyp_in();
  }
 if ( (r-y)<0 || (total-r)<0 || (n-y)<0 || (total-r-n+y)<0 || (total-n)<0 )
  {
  cout<<"\n**ERROR**";
  cout<<"\nMan this is not possible.";
  cout<<"\nYour entered data contains some serious errors in it. ";
  cout<<"\nSo it cannot be calculated. ";
  cout<<"\nEnter the new data again.\n";
  hyp_in();
  }
 }
void hyper::hyp_cal()
 {
 float f1 = fact(r) / ( fact(y) * fact(r-y) );
 float f2 = fact(total-r) / ( fact(n-y) * fact(total-r-n+y) );
 float f3 = fact(total) / ( fact(n) * fact(total-n) );
 prob = (f1 * f2) / f3;
 var = ( r * n * (total - r) * (total - n) ) / ( (total * total) * (total - 1.0) );
 mean = (1.0) * (n * r) / total;
 }
void hyper::hyp_show()
 {
 cout<<"\n\nThe Probability of the Hyper Geomatric Distribution p(y) is : "<<prob;
 cout<<"\n\nThe Variance of the Hyper Geomatric Distribution \xE5\xFD is : "<<var;
 cout<<"\n\nThe Mean of the Hyper Geomatric Distribution \xE6 is : "<<mean;
 cout<<"\n\nPress any key to go to DRV Menu ...";
 }
void hyper::hyp_complete()
 {
 clrscr();
 cout<<"\n\t\t\tHYPERGEOMATRIC DISTRIBUTION:\n";
 hyp_in();
 hyp_cal();
 hyp_show();
 hyper();
 getch();
 }
//////////////////////////////////////////////////////////////////////////////
class multi
 {
 private:
	char dn[50];
	boolean multist;
	float prob;	  			//probability of hyper distibution
	int n;     	        //number of trials
	char pch;				//char value of p
	float var;				//variance
	float mean;				//mean
	float p[50];          	//probability of each trial
	char ych[50];				//char value of y
	static int leny;			//length of y
	int y[50];            	//number of occurance of each outcome
 public:
	multi();
	void multiin_ny();		 	//gets the value of n & y
	void multiin_p();         	//gets the value of probabilty
	void check_frac();        	//checks whether the input is fraction or not
	void multi_cal();        	//calculates & shows the probability of multinomial distribution &
	void multi_varmen();          //calculates & shows variance & mean
	void multi_complete();			//prerforms complete operation
	friend float power(float, float); 	//calculates power
	friend double fact(int);	 	//calculates factorial
	void multifrac(char[]);
	void multichar(char[],boolean);
 };
void multi::multichar(char temp[],boolean)
 {
 boolean multiflag;
 multiflag=false;
 long a=0;
 for (int i=0; temp[i]!='\0';i++)
  {
  a=temp[i];
  if(multiflag==1)
   {
   if(a!=42)
    {
	if (a<46||a>57||a==47)
	 {
	 multiflag=true;
	 cout<<"\n**ERROR**\nPlease donot enter a character";
	 if (multist)
		multiin_ny();
	 else
		multiin_p();
	 }
    }
   else
	multiflag=false;
   } //endif
  }//endfor
 }
void multi:: multifrac(char temp[])
 {
 for ( int i=0; temp[i]!='\0'; i++ )
  {
  if ( temp[i] == '.' )
   {
   cout<<"**ERROR**";
   cout<<"\nYour numbers should not be a fraction.";
   cout<<"\nEnter the values again.\n ";
   multiin_ny();
   }
  }
 }
int multi::leny = 0;               //static leny
multi::multi()
 {
 n   = 0;
 var 	= 0;
 mean	= 0;
 prob 	= 0;
 leny = 0;
 for ( int i=0; i<50; i++ )
  {
  y[i] = 0;
  p[i] = 0;
  }
 pch = '\0';
 }
void multi::multiin_ny()
 {
 multist=false;
 cout<<"\nEnter the number of trials (n) : ";	cin>>dn;
 cout<<"\nEnter the number of occurances for each outcome y[i]. ";
 cout<<"\nPress * when you are done. \n";
 do
  {
  cout<<"\nEnter the value of outcome y["<<leny+1<<"] : "; cin>>ych;
  multifrac(dn);
  multichar(dn,multist);
  n=atoi(dn);
  multifrac(ych);
  multichar(ych,multist);
  y[leny++] = atoi(ych);
  }
 while ( *ych != '*' );
 cout<<"\nPress any key to continue....";
 leny--;
 getche();
 }
void multi::multiin_p()
 {
 multist=true;
 float sum = 0.0;
 clrscr();
 cout<<"\nEnter the Probability for each outcome p[i]. \n";
 for ( int i=0; i<leny; i++ )
  {
  cout<<"\nEnter the probability of outcome p("<<i+1<<") : ";
  cin>>p[i];
  }
 for ( int j=0; j<leny; j++ )
	sum = sum + p[j];
 if ( sum > 1.0 )
  {
  cout<<"\n**ERROR**\nThe sum of all the probabilities must be equal to 1\n";
  cout<<"\nPress any key to enter again";
  getch();
  multiin_p();
  }
 }
void multi::multi_cal()
 {
 double long profact_y[50];          //factorial of y[i]
 float yresult = 1.0;             //this result gives value of fact(y[1]) * fact(y[2]) * ..... * fact(y[n])
 float propow_p[50];              //p[i] raise to the power y[i]
 float presult = 1.0;             //this result gives value of pow(p[1],y[1]) * pow (p[2],y[2]) * ..... * pow(p[n],powy[n])
 for (int i=0; i<50; i++)           //initializing propow_p[] & profact_[]
  {
  propow_p[i]=0;
  profact_y[i]=0;
  }
 for (i=0; i<leny; i++ )
  {
  profact_y[i] = fact(y[i]);
  yresult = yresult * profact_y[i];
  }
 for ( int j=0; j<leny; j++ )
  {
  if ( y[i] == 0 )
   {
   propow_p[j] = power(p[j],y[j]);
   presult = presult * propow_p[j];
   }
  else
   {
   propow_p[j] = pow(p[j],y[j]);
   presult = presult * propow_p[j];
   }
  }
 prob = ( fact(n) * presult ) / yresult;
 cout<<"\nThe probability of the Multinomial Distribution is p(y[i]): "<<prob;
 cout<<"\n\nPress any key to continue...";
 getch();
 }
void multi::multi_varmen()
 {
 float mv_p = 0.0;
 int flag = 0;
 char sure;
 clrscr();
 cout<<"\n\nEnter the probability whose mean \xE6 & variance \xE5 you want to calculate :";
 cin>>mv_p;
 for ( int k=0; k<leny; k++ )
  {
  if ( mv_p == p[k] )
   {
   mean = n * p[k];
   var = n * p[k] * ( 1-p[k] );
   flag = 1;
   cout<<"\n\nThe Variance \xE5 of the element y["<<k<<"] is : "<<var;
   cout<<"\n\nThe Mean \xE5 of the element y["<<k<<"] is : "<<mean;
   }
  }
 if ( flag == 0 )
	cout<<"\nThe number you entered was not found";
 cout<<"\n\nWant to check the Mean & variance of any other number.";
 cout<<"\n\nPress 'y' for yes or 'n'for no : ";
 sure = getche();
 if ( sure == 'n' )
	cout<<"\n\nPress any key to go to DRV Menu ...";
 else
	multi_varmen();
 }
void multi::multi_complete()
 {
 clrscr();
 cout<<"\n\t\t\tMULTINOMIAL DISTRIBUTION:\n";
 multiin_ny();
 multiin_p();
 multi_cal();
 multi_varmen();
 multi();
 getch();
 }
//////////////////////////////////////////////////////////////////////////////
/////				FRIEND FUNCTIONS			 /////
//////////////////////////////////////////////////////////////////////////////
double fact(int temp)
 {
 if ( temp==0 )
	return 1;
 else
  {
  double t = temp * fact(temp-1);
  return t;
  }
 }
float power(float variable, float po)
 {
 float result = 1.0;
 if ( variable == 0 )
	return 0;
 else
  {
  for ( int i = 0; i < po; i++ )
	result = variable * result;
	return result;
  }
 }
//////////////////////////////////////////////////////////////////////////////
class drv_cal
 {
 public:
	drv_cal() : drv_srno(0)	{ }       //constructor to initialize the values of class drv_cal
	void drv_menu();            //DRV menu
	void drv_serial();			//DRV menu details
	void drv_quit();			//quits from DRV menu
 private:
	binomial b1;              //containership
	negative n1;              //containership
	poisson p1;               //containership
	hyper h1;                //containership
	multi m1;                //containership
	int drv_srno;				//serial number variable for DRV menu
 };
void drv_cal::drv_menu()
 {
 clrscr();
 cout<<"\n\tDISCRETE RANDOM VARIABLE MENU\n\n";
 cout<<"1. Binomial Distribution\n";
 cout<<"2. Multinomial Distribution\n";
 cout<<"3. Hyper Geomatric Distribution\n";
 cout<<"4. Negative Binomial Distribution\n";
 cout<<"5. Poisson Distribution\n";
 cout<<"6. Go to Main Menu\n";
 }
void drv_cal::drv_serial()
 {
 clrscr();
 drv_menu();
 drv_srno = 0;
 while (drv_srno != '6')
  {
  cout<<"\n\nEnter your choice from 1-6 from the menu : ";
  drv_srno = getche();
  cout<<"\n";
  switch(drv_srno)
   {
   case '1':		b1.bi_complete();		break;
   case '2':		m1.multi_complete();		break;
   case '3':  	h1.hyp_complete();		break;
   case '4':  	n1.neg_complete();		break;
   case '5':  	p1.pos_complete();		break;
   case '6':  	drv_quit();			break;
   default:
   cout<<"\n\t**ERROR 1-6 only allowed**";
   cout<<"\n\n\tPress any key to continue...";
   getche();
   }//end switch
  cout<<"\n";
  clrscr();
  drv_menu();
  }//end while
 }
void drv_cal::drv_quit()
 {
 char sure;
 cout<<"\n\nAre you sure you want to quit from DRV Menu.";
 cout<<"\n\nPress 'y' for yes or 'n' for no : ";
 sure = getche();
 if ( sure == 'y' )
  {
  cout<<"\n\nQuiting from DRV menu\n";
  cout<<"\n\t\t\t\t\t\tPress any key to continue.......";
  getch();
  }
 else
	drv_serial();
 }
//////////////////////////////////////////////////////////////////////////////
class mainmenu : public dis_cal, public drv_cal
 {
 public:
	mainmenu() : dis_srno(0) { }
	void mmn_menu();
	void mmn_serial();
	void mmn_quit();
 private:
	int dis_srno;
 };
void mainmenu::mmn_menu()
 {
 cout<<"\n\t\t\t******** MAIN MENU ********\n";
 cout<<"\n\t\t\t1. Discrete Random Variable";
 cout<<"\n\t\t\t2. Descriptive Statistics";
 cout<<"\n\t\t\t3. Quit Program";
 }
void mainmenu::mmn_serial()
 {
 clrscr();
 mmn_menu();
 dis_srno = 0;
 while ( dis_srno != '3' )
  {
  cout<<"\n\nEnter your choice from 1-3 from the menu : ";
  dis_srno = getche();
  cout<<"\n";
  switch(dis_srno)
   {
   case '1':		drv_cal::drv_serial();		break;
   case '2':  	dis_cal::in_serial();		break;
   case '3':  	mmn_quit();   		break;
   default:
   cout<<"\n\t**ERROR 1-3 only allowed**";
   cout<<"\n\n\tPress any key to continue...";
   getche();
   }//end switch
  cout<<"\n";
  clrscr();
  mmn_menu();
  }//end while
 }
void mainmenu::mmn_quit()
 {
 char sure;
 cout<<"\n\nAre you sure you want to quit.";
 cout<<"\n\nPress 'y' for yes or 'n' for no. : ";
 sure = getche();
 if ( sure == 'y' )
  {
  cout<<"\n\n\n\n\n\n\n\n\tSee ya next time ....\x01 \x01 \x01 \x01 Bubye ";
  cout<<"\x01 \x01 \x01 \x01 \n\n\t\tHave a nice day !!!!\n";
  cout<<"\t\t\t\t\t\tPress any key to quit........";
  getch();
  }
 else
	mmn_serial();
 }
main()
 {
 clrscr();
 cout<<"\n\n\tEnd Term Project\n\n\tC++\n\n\tProject Title\n\n";
 cout<<"\t\tSTATLAB";
 cout<<"\n\n\n\n\n\n\n\n\n\t\tPress any key to enter into the \"WORLD OF STATISTICS\".......";
 getche();
 clrscr();
 mainmenu wow;
 wow.mmn_serial();
 return 0;
 }
```

