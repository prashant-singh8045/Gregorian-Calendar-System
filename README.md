# Gregorian-Calendar-System
#include<stdio.h>
#include<conio.h>
#include<dos.h>
//dd,ld,mm,yyyy,lc,cc,sum,a,b,c,j,d;
//dd means date
//ld means last date of month
//mm means month
//yyyy means given year
//lc is check leap
//cc is check century for 100,200,300,400 year
//sum means sum of total days from 1 jan 0001 to date/given month/given year
//a is 'var' from 1st to (given year-1) for looping
//b is 'var' from 1st to (given month-1) for looping
//c is 'var' to check day from 1 to 7
//j is column
//d is local date
int day();
int month();
int year();
int main()
{
    int dd,ld,mm,yyyy,lc,cc,sum,a,b,c,j,num;
    struct date d;
    getdate(&d);
    printf("today:- %d/%d/%d\n",d.da_day,d.da_mon,d.da_year);
    dd=1;
    mm=d.da_mon;
    yyyy=d.da_year;
    sum=1;
    a=1;
    b=1;
    lc=yyyy%4;
    cc=yyyy%400;
    for(a=1; a<yyyy; a++)
    {
	lc=a%4;
	cc=a%400;
	if(lc>0&cc>0)
	{
	    sum=sum+365;
	}
	else if(lc==0&cc==100)
	{
	    sum=sum+365;
	}
	else if(lc==0&cc==200)
	{
	    sum=sum+365;
	}
	else if(lc==0&cc==300)
	{
	    sum=sum+365;
	}
	else if(lc==0&cc==0)
	{
	    sum=sum+366;
	}
	else if(lc==0&cc>0)
	{
	    sum=sum+366;
	}
    }
    sum=sum+dd;
    lc=yyyy%4;
    cc=yyyy%400;
    for(b=1; b<mm; b++)
    {
	if(b==1)
	{
	    sum=sum+31;
	}
	else if(b==2&lc>0&cc>0)
	{
	    sum=sum+28;
	}
	else if(b==2&lc==0&cc==100)
	{
	    sum=sum+28;
	}
	else if(b==2&lc==0&cc==200)
	{
	    sum=sum+28;
	}
	else if(b==2&lc==0&cc==300)
	{
	    sum=sum+28;
	}
	else if(b==2&lc==0&cc==0)
	{
	    sum=sum+29;
	}
	else if(b==2&lc==0&cc>0)
	{
	    sum=sum+29;
	}
	else if(b==3)
	{
	    sum=sum+31;
	}
	else if(b==4)
	{
	    sum=sum+30;
	}
	else if(b==5)
	{
	    sum=sum+31;
	}
	else if(b==6)
	{
	    sum=sum+30;
	}
	else if(b==7)
	{
	    sum=sum+31;
	}
	else if(b==8)
	{
	    sum=sum+31;
	}
	else if(b==9)
	{
	    sum=sum+30;
	}
	else if(b==10)
	{
	    sum=sum+31;
	}
	else if(b==11)
	{
	    sum=sum+30;
	}
    }
    if(mm==1)
    {
	printf("January:-");
	ld=31;
    }
    else if(mm==2&lc>0&cc>0)
    {
	printf("Feburary:-");
	ld=28;
    }
    else if(mm==2&lc==0&cc==100)
    {
	printf("Feburary:-");
	ld=28;
    }
    else if(mm==2&lc==0&cc==200)
    {
	printf("Feburary:-");
	ld=28;
    }
    else if(mm==2&lc==0&cc==300)
    {
	printf("Feburary:-");
	ld=28;
    }
    else if(mm==2&lc==0&cc==0)
    {
	printf("Feburary:-");
	ld=29;
    }
    else if(mm==2&lc==0&cc>0)
    {
	printf("Feburary:-");
	ld=29;
    }
    else if(mm==3)
    {
	printf("march:-");
	ld=31;
    }
    else if(mm==4)
    {
	printf("april:-");
	ld=30;
    }
    else if(mm==5)
    {
	printf("may:-");
	ld=31;
    }
    else if(mm==6)
    {
	printf("june:-");
	ld=30;
    }
    else if(mm==7)
    {
	printf("July:-");
	ld=31;
    }
    else if(mm==8)
    {
	printf("august:-");
	ld=31;
    }
    else if(mm==9)
    {
	printf("september:-");
	ld=30;
    }
    else if(mm==10)
    {
	printf("october:-");
	ld=31;
    }
    else if(mm==11)
    {
	printf("November:-");
	ld=30;
    }
    else if(mm==12)
    {
	printf("December:-");
	ld=31;
    }
    printf("\n");
    textcolor(4);
    {
	cprintf("sun ");
    }
    printf("mon tue wed thu fri sat\n");
    printf("---------------------------\n");
    c=sum%7;
    for(j=0; j<=41; j++)
    {
	if(j<c)
	{
	    printf("    ");
	}
	else if(j>=c)
	{
	    if(dd<=ld)
	    {
		if(dd<10)
		{
		    if(j==0|j==7|j==14|j==21|j==28|j==35)
		    {
			if(dd==d.da_day&mm==d.da_mon&yyyy==d.da_year)
			{
			    textcolor(2);
			    cprintf("  %d ",dd);
			}
			else
			{
			    textcolor(4);
			    cprintf("  %d ",dd);
			}
		    }
		    else
		    {
			if(dd==d.da_day&mm==d.da_mon&yyyy==d.da_year)
			{
			    textcolor(2);
			    cprintf("  %d ",dd);
			}
			else
			{
			    printf("  %d ",dd);
			}
		    }
		}
		else if(dd>=10)
		{
		    if(j==0|j==7|j==14|j==21|j==28|j==35)
		    {
			if(dd==d.da_day&mm==d.da_mon&yyyy==d.da_year)
			{
			    textcolor(2);
			    cprintf(" %d ",dd);
			}
			else
			{
			    textcolor(4);
			    cprintf(" %d ",dd);
			}
		    }
		    else
		    {
			if(dd==d.da_day&mm==d.da_mon&yyyy==d.da_year)
			{
			    textcolor(2);
			    cprintf(" %d ",dd);
			}
			else
			{
			    printf(" %d ",dd);
			}
		    }
		}
		if(j==6|j==13|j==20|j==27|j==34)
		{
		    printf("\n");
		}
		dd++;
	    }
	    else if(dd>ld)
	    {
		printf("\n");
		break;
	    }
	}
    }
    printf("\n---------------------------------\n");
    printf("MAIN MENU:-\n");
    printf("1. Enter 1 to see day from date\n");
    printf("2. Enter 2 to see particular month chart\n");
    printf("3. Enter 3 to see year calander\n\n");
    scanf("%d",&num);
    clrscr();
    if(num<1|num>3)
    {
	printf("invalid input\n\n");
	main();
    }
    else if(num==1)
    {
	day();
    }
    else if(num==2)
    {
	month();
    }
    else if(num==3)
    {
	year();
    }
    getchar();
    return 0;
}
int day()
{
    int dd, mm, yyyy, lc, cc, sum, a, b, c;
    printf("find day from date\n");
    printf("NOTE-enter 0 to go back to main menu\n");
    printf("enter date:-");
    scanf("%d",&dd);
    if(dd==0)
    {
	clrscr();
	printf("going back to main menu\n\n");
	main();
    }
    else if(dd>0)
    {
	printf("enter month:-");
	scanf("%d",&mm);
	printf("enter year:-");
	scanf("%d",&yyyy);
	clrscr();
	printf("%d/%d/%d= ",dd,mm,yyyy);
	lc=yyyy%4;
	cc=yyyy%400;
	sum=1;
	a=1;
	b=1;
	if(mm==0|mm>12|yyyy==0)
	{
	    printf("invalid input\n\n");
	    day();
	}
	else if(mm==1&dd>31&yyyy>0)
	{
	    printf("invalid input\n");
	    printf("In January- max date is 31\n\n");
	    day();
	}
	else if(mm==3&dd>31&yyyy>0)
	{
	    printf("invalid input\n");
	    printf("In march- max date is 31\n\n");
	    day();
	}
	else if(mm==4&dd>30&yyyy>0)
	{
	    printf("invalid input\n");
	    printf("In april- max date is 30\n\n");
	    day();
	}
	else if(mm==5&dd>31&yyyy>0)
	{
	    printf("invalid input\n");
	    printf("In may- max date is 31\n\n");
	    day();
	}
	else if(mm==6&dd>30&yyyy>0)
	{
	    printf("invalid input\n");
	    printf("In june- max date is 30\n\n");
	    day();
	}
	else if(mm==7&dd>31&yyyy>0)
	{
	    printf("invalid input\n");
	    printf("In July- max date is 31\n\n");
	    day();
	}
	else if(mm==8&dd>31&yyyy>0)
	{
	    printf("invalid input\n");
	    printf("In august- max date is 31\n\n");
	    day();
	}
	else if(mm==9&dd>30&yyyy>0)
	{
	    printf("invalid input\n");
	    printf("In september- max date is 30\n\n");
	    day();
	}
	else if(mm==10&dd>31&yyyy>0)
	{
	    printf("invalid input\n");
	    printf("In October- max date is 31\n\n");
	    day();
	}
	else if(mm==11&dd>30&yyyy>0)
	{
	    printf("invalid input\n");
	    printf("In November- max date is 30\n\n");
	    day();
	}
	else if(mm==12&dd>31&yyyy>0)
	{
	    printf("invalid input\n");
	    printf("In December- max date is 31\n\n");
	    day();
	}
	else if(mm==2&dd>28&yyyy>0&lc>0)
	{
	    printf("invalid input\n");
	    printf("it's not a leap year\n");
	    printf("so in Feburary- max date is 28\n\n");
	    day();
	}
	else if(mm==2&dd>28&yyyy>0&lc==0&cc==100)
	{
	    printf("invalid input\n");
	    printf("it's not a leap year\n");
	    printf("so in Feburary- max date is 28\n\n");
	    day();
	}
	else if(mm==2&dd>28&yyyy>0&lc==0&cc==200)
	{
	    printf("invalid input\n");
	    printf("it's not a leap year\n");
	    printf("so in Feburary- max date is 28\n\n");
	    day();
	}
	else if(mm==2&dd>28&yyyy>0&lc==0&cc==300)
	{
	    printf("invalid input\n");
	    printf("it's not a leap year\n");
	    printf("so in Feburary- max date is 28\n\n");
	    day();
	}
	else if(mm==2&dd>29&yyyy>0&lc==0&cc==0)
	{
	    printf("invalid input\n");
	    printf("it's a leap year\n");
	    printf("so in Feburary- max date is 29\n\n");
	    day();
	}
	else if(mm==2&dd>29&yyyy>0&lc==0&cc>0)
	{
	    printf("invalid input\n");
	    printf("it's a leap year\n");
	    printf("so in Feburary- max date is 29\n\n");
	    day();
	}
	for(a=1; a<yyyy; a++)
	{
	    lc=a%4;
	    cc=a%400;
	    if(lc>0&cc>0)
	    {
		sum=sum+365;
	    }
	    else if(lc==0&cc==100)
	    {
		sum=sum+365;
	    }
	    else if(lc==0&cc==200)
	    {
		sum=sum+365;
	    }
	    else if(lc==0&cc==300)
	    {
		sum=sum+365;
	    }
	    else if(lc==0&cc==0)
	    {
		sum=sum+366;
	    }
	    else if(lc==0&cc>0)
	    {
		sum=sum+366;
	    }
	}
	sum=sum+dd;
	lc=yyyy%4;
	cc=yyyy%400;
	for(b=1; b<mm; b++)
	{
	    if(b==1)
	    {
		sum=sum+31;
	    }
	    else if(b==2&lc>0&cc>0)
	    {
		sum=sum+28;
	    }
	    else if(b==2&lc==0&cc==100)
	    {
		sum=sum+28;
	    }
	    else if(b==2&lc==0&cc==200)
	    {
		sum=sum+28;
	    }
	    else if(b==2&lc==0&cc==300)
	    {
		sum=sum+28;
	    }
	    else if(b==2&lc==0&cc==0)
	    {
		sum=sum+29;
	    }
	    else if(b==2&lc==0&cc>0)
	    {
		sum=sum+29;
	    }
	    else if(b==3)
	    {
		sum=sum+31;
	    }
	    else if(b==4)
	    {
		sum=sum+30;
	    }
	    else if(b==5)
	    {
		sum=sum+31;
	    }
	    else if(b==6)
	    {
		sum=sum+30;
	    }
	    else if(b==7)
	    {
		sum=sum+31;
	    }
	    else if(b==8)
	    {
		sum=sum+31;
	    }
	    else if(b==9)
	    {
		sum=sum+30;
	    }
	    else if(b==10)
	    {
		sum=sum+31;
	    }
	    else if(b==11)
	    {
		sum=sum+30;
	    }
	}
	c=sum%7;
	if(c==1)
	{
	    printf("it's monday\n");
	}
	else if(c==2)
	{
	    printf("it's Tuesday\n");
	}
	else if(c==3)
	{
	    printf("it's Wednesday\n");
	}
	else if(c==4)
	{
	    printf("it's Thursday\n");
	}
	else if(c==5)
	{
	    printf("it's Friday\n");
	}
	else if(c==6)
	{
	    printf("it's Saturday\n");
	}
	else if(c==0)
	{
	    printf("it's Sunday\n");
	}
	printf("---------------------------------\n");
	day();
    }
    return 0;
}
int month()
{
    int dd,ld,mm,yyyy,lc,cc,sum,a,b,c,j;
    printf("see month chart\n");
    printf("NOTE-enter 0 to go back to main menu\n");
    struct date d;
    getdate(&d);
    printf("enter month:-");
    scanf("%d",&mm);
    if(mm==0)
    {
	clrscr();
	printf("going back to main menu\n\n");
	main();
    }
    else if(mm>0)
    {
	printf("enter year:-");
	scanf("%d",&yyyy);
	clrscr();
	printf("month=%d, year=%d\n",mm,yyyy);
	dd=1;
	sum=1;
	a=1;
	b=1;
	lc=yyyy%4;
	cc=yyyy%400;
	if(mm>12|yyyy==0)
	{
	    printf("invalid input\n\n");
	    month();
	}
	for(a=1; a<yyyy; a++)
	{
	    lc=a%4;
	    cc=a%400;
	    if(lc>0&cc>0)
	    {
		sum=sum+365;
	    }
	    else if(lc==0&cc==100)
	    {
		sum=sum+365;
	    }
	    else if(lc==0&cc==200)
	    {
		sum=sum+365;
	    }
	    else if(lc==0&cc==300)
	    {
		sum=sum+365;
	    }
	    else if(lc==0&cc==0)
	    {
		sum=sum+366;
	    }
	    else if(lc==0&cc>0)
	    {
		sum=sum+366;
	    }
	}
	sum=sum+dd;
	lc=yyyy%4;
	cc=yyyy%400;
	for(b=1; b<mm; b++)
	{
	    if(b==1)
	    {
		sum=sum+31;
	    }
	    else if(b==2&lc>0&cc>0)
	    {
		sum=sum+28;
	    }
	    else if(b==2&lc==0&cc==100)
	    {
		sum=sum+28;
	    }
	    else if(b==2&lc==0&cc==200)
	    {
		sum=sum+28;
	    }
	    else if(b==2&lc==0&cc==300)
	    {
		sum=sum+28;
	    }
	    else if(b==2&lc==0&cc==0)
	    {
		sum=sum+29;
	    }
	    else if(b==2&lc==0&cc>0)
	    {
		sum=sum+29;
	    }
	    else if(b==3)
	    {
		sum=sum+31;
	    }
	    else if(b==4)
	    {
		sum=sum+30;
	    }
	    else if(b==5)
	    {
		sum=sum+31;
	    }
	    else if(b==6)
	    {
		sum=sum+30;
	    }
	    else if(b==7)
	    {
		sum=sum+31;
	    }
	    else if(b==8)
	    {
		sum=sum+31;
	    }
	    else if(b==9)
	    {
		sum=sum+30;
	    }
	    else if(b==10)
	    {
		sum=sum+31;
	    }
	    else if(b==11)
	    {
		sum=sum+30;
	    }
	}
	printf("%d/%d/%d\n",d.da_day,d.da_mon,d.da_year);
	if(mm==1)
	{
	    printf("\nJanuary:-");
	    ld=31;
	}
	else if(mm==2&lc>0&cc>0)
	{
	    printf("\nFeburary:-");
	    ld=28;
	}
	else if(mm==2&lc==0&cc==100)
	{
	    printf("\nFeburary:-");
	    ld=28;
	}
	else if(mm==2&lc==0&cc==200)
	{
	    printf("\nFeburary:-");
	    ld=28;
	}
	else if(mm==2&lc==0&cc==300)
	{
	    printf("\nFeburary:-");
	    ld=28;
	}
	else if(mm==2&lc==0&cc==0)
	{
	    printf("\nFeburary:-");
	    ld=29;
	}
	else if(mm==2&lc==0&cc>0)
	{
	    printf("\nFeburary:-");
	    ld=29;
	}
	else if(mm==3)
	{
	    printf("\nmarch:-");
	    ld=31;
	}
	else if(mm==4)
	{
	    printf("\napril:-");
	    ld=30;
	}
	else if(mm==5)
	{
	    printf("\nmay:-");
	    ld=31;
	}
	else if(mm==6)
	{
	    printf("\nJune:-");
	    ld=30;
	}
	else if(mm==7)
	{
	    printf("\nJuly:-");
	    ld=31;
	}
	else if(mm==8)
	{
	    printf("\naugust:-");
	    ld=31;
	}
	else if(mm==9)
	{
	    printf("\nSeptember:-");
	    ld=30;
	}
	else if(mm==10)
	{
	    printf("\nOctober:-");
	    ld=31;
	}
	else if(mm==11)
	{
	    printf("\nNovember:-");
	    ld=30;
	}
	else if(mm==12)
	{
	    printf("\nDecember:-");
	    ld=31;
	}
	printf("\n");
	textcolor(4);
	{
	    cprintf ("sun ");
	}
	printf("mon tue wed thu fri sat\n");
	printf("---------------------------\n");
	c=sum%7;
	for(j=0; j<=41; j++)
	{
	    if(j<c)
	    {
		printf("    ");
	    }
	    else if(j>=c)
	    {
		if(dd<=ld)
		{
		    if(dd<10)
		    {
			if(j==0|j==7|j==14|j==21|j==28|j==35)
			{
			    if(dd==d.da_day&mm==d.da_mon&yyyy==d.da_year)
			    {
				textcolor(2);
				cprintf("  %d ",dd);
			    }
			    else
			    {
				textcolor(4);
				cprintf("  %d ",dd);
			    }
			}
			else
			{
			    if(dd==d.da_day&mm==d.da_mon&yyyy==d.da_year)
			    {
				textcolor(2);
				cprintf("  %d ",dd);
			    }
			    else
			    {
				printf("  %d ",dd);
			    }
			}
		    }
		    else if(dd>=10)
		    {
			if(j==0|j==7|j==14|j==21|j==28|j==35)
			{
			    if(dd==d.da_day&mm==d.da_mon&yyyy==d.da_year)
			    {
				textcolor(2);
				cprintf(" %d ",dd);
			    }
			    else
			    {
				textcolor(4);
				cprintf(" %d ",dd);
			    }
			}
			else
			{
			    if(dd==d.da_day&mm==d.da_mon&yyyy==d.da_year)
			    {
				textcolor(2);
				cprintf(" %d ",dd);
			    }
			    else
			    {
				printf(" %d ",dd);
			    }
			}
		    }
		    if(j==6|j==13|j==20|j==27|j==34)
		    {
			printf("\n");
		    }
		    dd++;
		}
		else if(dd>ld)
		{
		    printf("\n");
		    break;
		}
	    }
	}
	printf("\n---------------------------------\n");
	month();
    }
    return 0;
}
int year()
{
    int dd,ld,mm,yyyy,lc,cc,sum,a,b,c,j;
    printf("enter year to see calender\n");
    printf("NOTE-enter 0 to go back to main menu\n");
    struct date d;
    getdate(&d);
    printf("enter year:-");
    scanf("%d",&yyyy);
    clrscr();
    printf("%d/%d/%d\n",d.da_day,d.da_mon,d.da_year);
    printf("year=%d\n",yyyy);
    dd=1;
    mm=1;
    sum=1;
    a=1;
    b=1;
    lc=yyyy%4;
    cc=yyyy%400;
    if(yyyy==0)
    {
        printf("going to main menu\n\n");
        main();
    }
    else if(yyyy>0)
    {
        for(mm=1; mm<13; mm++)
        {
            for(a=1; a<yyyy; a++)
            {
                lc=a%4;
                cc=a%400;
                if(lc>0&cc>0)
                {
                    sum=sum+365;
                }
                else if(lc==0&cc==100)
                {
                    sum=sum+365;
                }
                else if(lc==0&cc==200)
                {
                    sum=sum+365;
                }
                else if(lc==0&cc==300)
                {
                    sum=sum+365;
                }
                else if(lc==0&cc==0)
                {
                    sum=sum+366;
                }
                else if(lc==0&cc>0)
                {
                    sum=sum+366;
                }
            }
            sum=sum+dd;
            lc=yyyy%4;
            cc=yyyy%400;
            for(b=1; b<mm; b++)
            {
                if(b==1)
                {
                    sum=sum+31;
                }
                else if(b==2&lc>0&cc>0)
                {
                    sum=sum+28;
                }
                else if(b==2&lc==0&cc==100)
                {
                    sum=sum+28;
                }
                else if(b==2&lc==0&cc==200)
                {
                    sum=sum+28;
                }
                else if(b==2&lc==0&cc==300)
                {
                    sum=sum+28;
                }
                else if(b==2&lc==0&cc==0)
                {
                    sum=sum+29;
                }
                else if(b==2&lc==0&cc>0)
                {
                    sum=sum+29;
                }
                else if(b==3)
                {
                    sum=sum+31;
                }
                else if(b==4)
                {
                    sum=sum+30;
                }
                else if(b==5)
                {
                    sum=sum+31;
                }
                else if(b==6)
                {
                    sum=sum+30;
                }
                else if(b==7)
                {
                    sum=sum+31;
                }
                else if(b==8)
                {
                    sum=sum+31;
                }
                else if(b==9)
                {
                    sum=sum+30;
                }
                else if(b==10)
                {
                    sum=sum+31;
                }
                else if(b==11)
                {
                    sum=sum+30;
                }
            }
            if(mm==1)
            {
                printf("\nJanuary:-");
                ld=31;
            }
            else if(mm==2&lc>0&cc>0)
            {
                printf("\nFeburary:-");
                ld=28;
            }
            else if(mm==2&lc==0&cc==100)
            {
                printf("\nFeburary:-");
                ld=28;
            }
            else if(mm==2&lc==0&cc==200)
            {
                printf("\nFeburary:-");
                ld=28;
            }
            else if(mm==2&lc==0&cc==300)
            {
                printf("\nFeburary:-");
                ld=28;
            }
            else if(mm==2&lc==0&cc==0)
            {
                printf("\nFeburary:-");
                ld=29;
            }
            else if(mm==2&lc==0&cc>0)
            {
                printf("\nFeburary:-");
                ld=29;
            }
            else if(mm==3)
            {
                printf("\nmarch:-");
                ld=31;
            }
            else if(mm==4)
            {
                printf("\napril:-");
                ld=30;
            }
            else if(mm==5)
            {
                printf("\nmay:-");
                ld=31;
            }
            else if(mm==6)
            {
                printf("\nJune:-");
                ld=30;
            }
            else if(mm==7)
            {
                printf("\nJuly:-");
                ld=31;
            }
            else if(mm==8)
            {
                printf("\naugust:-");
                ld=31;
            }
            else if(mm==9)
            {
                printf("\nSeptember:-");
                ld=30;
            }
            else if(mm==10)
            {
                printf("\nOctober:-");
                ld=31;
            }
            else if(mm==11)
            {
                printf("\nNovember:-");
                ld=30;
            }
            else if(mm==12)
            {
                printf("\nDecember:-");
                ld=31;
            }
            printf("\n");
            textcolor(4);
            {
                cprintf("sun ");
            }
            printf("mon tue wed thu fri sat\n");
            printf("---------------------------\n");
            c=sum%7;
            for(j=0; j<=41; j++)
            {
                if(j<c)
                {
                    printf("    ");
                }
                else if(j>=c)
                {
                    if(dd<=ld)
                    {
                        if(dd<10)
                        {
                            if(j==0|j==7|j==14|j==21|j==28|j==35)
                            {
                                if(dd==d.da_day&mm==d.da_mon&yyyy==d.da_year)
                                {
                                    textcolor(2);
                                    cprintf("  %d ",dd);
                                }
                                else
                                {
                                    textcolor(4);
                                    cprintf("  %d ",dd);
                                }
                            }
                            else
                            {
                                if(dd==d.da_day&mm==d.da_mon&yyyy==d.da_year)
                                {
                                    textcolor(2);
                                    cprintf("  %d ",dd);
                                }
                                else
                                {
                                    printf("  %d ",dd);
                                }
                            }
                        }
                        else if(dd>=10)
                        {
                            if(j==0|j==7|j==14|j==21|j==28|j==35)
                            {
                                if(dd==d.da_day&mm==d.da_mon&yyyy==d.da_year)
                                {
                                    textcolor(2);
                                    cprintf(" %d ",dd);
                                }
                                else
                                {
                                    textcolor(4);
                                    cprintf(" %d ",dd);
                                }
                            }
                            else
                            {
                                if(dd==d.da_day&mm==d.da_mon&yyyy==d.da_year)
                                {
                                    textcolor(2);
                                    cprintf(" %d ",dd);
                                }
                                else
                                {
                                    printf(" %d ",dd);
                                }
                            }
                        }
                        if(j==6|j==13|j==20|j==27|j==34)
                        {
                            printf("\n");
                        }
                        dd++;
                    }
                    else if(dd>ld)
                    {
                        printf("\n");
                        break;
                    }
                }
            }
            dd=1;
            sum=0;
        }
        printf("---------------------------------\n");
        year();
    }
    return 0;
}
