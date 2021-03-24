# DSA_Grph
All about DSA
class Solution:
    def pycycle1(self,s,visited,adj,parent):
        visited[s]=True
        for j in adj[s]:
            if (visited[j]==False):
                if (self.pycycle1(j,visited,adj,s)==True):
                    return True
            elif(j != parent):
                return True
        return False
    def isCycle(self, V, adj):
	    visited=[False]*(len(adj))
	    
	    for i in range(len(adj)):
	        if (visited[i]==False):
	            if (self.pycycle1(i,visited,adj,-1)==True):
	                return True
	    return False
