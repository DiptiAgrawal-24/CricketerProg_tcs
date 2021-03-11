# CricketerProg_tcs
class player:
    name="";
    country="";
    runs=0;
    age=0;
    no_of_matches=0;
    no_of_wickets=0;

    def __init__(self,p,q,r,s,t,u):
        self.name=p;
        self.country=q;
        self.runs=r;
        self.age=s;
        self.no_of_matches=t;
        self.no_of_wickets=u;


class team:
    def __init__(self,list):
        self.list=list;

    def getmin(self,list):
        min= 0;
        k=0;
        for j in list:
            if j.runs < list[min].runs:
                min = k;
            k=k+1;
        return list[min];
    def getmaxw(self,list):
        max=0;
        k=0;
        for i in list:
            if i.no_of_wickets > list[max].no_of_wickets:
                max = k;
            k = k+1;
        return list[max];

if __name__ == "__main__":
    n = int(input("enter number of players =>"))
    list = [];
    i=0;
    for i in range(n):
        p = input("enter name=")
        q = input("enter country=")
        r = int(input("enter runs="))
        s = int(input("enter age="))
        t = int(input("enter no of matches="))
        u= int(input("enter no of wickets="))
        list.append(player(p,q,r,s,t,u))
        ans = [];
    obj = team(list);
    ans.append(obj.getmin(list));
    ans.append(obj.getmaxw(list));
    print("name of min run scorer")
    print(ans[0].name)
    print("name of max wicket taker")
    print(ans[1].name)
