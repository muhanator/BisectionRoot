%Function name:
    function Xs=BisectionRoot(fun,a,b,tol) 
    fun=inline(fun)
    
%Initializing the iteration counter to 0:
    iteration=0; 

%If f(a)*f(b) is greater than 0, then no root exits and will display error
%message:
    if fun(a)*fun(b)>0
        disp('ERROR: no root exists between those points')
        
%If root does exist:
    else 
  %finds the first bisection and error value:
    Xs=((a+b)/2);
    err=abs((b-a)/2); 
    
%while the error is more than the allowed tolerance:
    while err>tol  
      %multiply the two functions and if answer is <0, b becomes Xs:
        if fun(a)*fun(Xs)<0 
            b=Xs;
      %Otherwise a becomes Xs:
        else
        end
        
    %calculating the new Xs and checking for error:
        Xs=(a+b)/2
        
    %If the error is > the allowed tolerance, the while loop will start
    %again:
        err=abs((b-a)/2); 
        
    %increment iteration counter by 1 everytime the while loop runs again
        iteration=iteration+1; 
 %end of while loop:
    end 
    end 

%display total iterations to find root:
    disp('Number of iterations: ');
    disp(iteration);  
 %End of program:
    end 