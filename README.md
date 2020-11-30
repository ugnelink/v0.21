# v0.21

#include <iostream>
#include <iomanip>
#include <fstream> 
using namespace std;
struct paz{string pav; string var; int p[7];float vid; float med; float sum;};

paz b[100];
main() {
int n=0;
ifstream df("kursiokai.txt");
ofstream rf("Rez.txt");
while (!df.eof()) {
n=n+1;
b[n].sum=0; 
df >> b[n].pav >> b[n].var;
for(int i=1; i<=6; i++) { df >> b[n].p[i]; b[n].sum=b[n].sum+b[n].p[i];}
b[n].vid=b[n].sum/6;

if(n%2==1) med=b[(n+1)/2].vid; else med=( b[n/2].vid+b[(n/2)+1].vid ) /2;
	cout <<"mediana yra: " << med << endl; 
 }
df.close(); 


for (int i=1; i<=n-1; i++)  { 
rf << fixed; 
rf << setprecision(2);
rf << b[i].var << " " <<  b[i].pav << " " <<   b[i].vid  << endl;

}
 rf.close(); return 0; 
  
} 
