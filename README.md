# -wandeli
#include<iostream>
#include<cmath>
using namespace std;
class matrix{
	private:
		 int hang;
		 int lie; 
		double mat[20][20] ;
	public:
		matrix( const int &ha, int &li){
			hang=ha;lie=li;
			}
		matrix(){
			hang=0;lie=0;
		} 
	    bool input(){
	    	cout<<"请输入"<<endl;
			for(int i=0;i<hang;i++)
			   for(int j=0;j<lie;j++)
			   cin>>mat[i][j]; 
		}
		int getvalue(int o,int p){
			int q;
			q=mat[o][p];
			return q;
		}
		bool print(){
			int i ,j,q;
			for( i=0;i<hang;i++){
		    cout<<endl;
			   for( j=0;j<lie;j++)
			     cout<<mat[i][j]<<'\0';
			  }	   
		    cout<<endl;
		}
		int ma_cheng(matrix &l,matrix &w){
			if(lie!=l.hang)
			cout<<"行不等于列"<<endl;
			else{
			int i,j,k;
			w.hang=hang;
			w.lie=l.lie;
			for( i=0;i<hang;i++)
			   for( j=0;j<l.lie;j++)
			   {
			   w.mat[i][j]=0;
			   for(k=0;k<lie;k++)
			   w.mat[i][j]= w.mat[i][j]+mat[i][k]*l.mat[k][j]; 
		}
		}
		return 0;
		}
		
};
int main(){
	int m,n,i,j,o,p;
	cout<<"请输入矩阵的行与列"<<endl;
	cin>>m>>n; 
	matrix s(m,n);
	s.input();
	s.print();
	cout<<"请输入矩阵的行与列"<<endl;
	cin>>o>>p; 
	matrix t(o,p);
	t.input();
	t.print();
	matrix ww;
	s.ma_cheng(t,ww);
	ww.print();
  }
