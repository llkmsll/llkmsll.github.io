---
layout: post
title: Soliloquy Of The Solipsist
date: 2015-07-06 07:59:00
---
I?    
I walk alone;    
The midnight street    
Spins itself from under my feet;    
When my eyes shut    
These dreaming houses all snuff out;    
Through a whim of mine    
Over gables the moon's celestial onion    
Hangs high.    
    
I    
Make houses shrink    
And trees diminish    
By going far; my look's leash    
Dangles the puppet-people    
Who, unaware how they dwindle,    
Laugh, kiss, get drunk,    
Nor guess that if I choose to blink    
They die.    
    
I    
When in good humor,    
Give grass its green    
Blazon sky blue, and endow the sun    
With gold;    
Yet, in my wintriest moods, I hold    
Absolute power    
To boycott any color and forbid any flower    
To be.    
    
I    
Know you appear    
Vivid at my side,    
Denying you sprang out of my head,    
Claiming you feel    
Love fiery enough to prove flesh real,    
Though it's quite clear    
All you beauty, all your wit, is a gift, my dear,    
From me.   


	 
### Sylvia Plath

{% highlight c++ %}

#include <bits/stdc++.h>
#define value first
#define idx second

using namespace std;
using pp = pair<int,int>;

int n,t,res,cnt,last;
deque<pp> minQ,maxQ;
int main(){
	scanf("%d %d",&t,&n);
	for(int i=1;i<=n;i++){
		int x;
		scanf("%d",&x);
		while(minQ.size() && minQ.back().value >= x) minQ.pop_back();
		while(maxQ.size() && maxQ.back().value <= x) maxQ.pop_back();
		minQ.push_back({x,i});
		maxQ.push_back({x,i});
		while(maxQ.front().value - minQ.front().value > t){
			if(maxQ.front().idx > minQ.front().idx){
				last = minQ.front().idx;
				minQ.pop_front();
			}
			else{ 
				last = maxQ.front().idx;
				maxQ.pop_front();
			}
		}
		res = max(res,i - last);
	}
	printf("%d",res);
}

{% endhighlight %}