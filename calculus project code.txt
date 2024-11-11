%EXPLANATION OF COMMANDS. FUNCTIONS AND TOOLBOXES:
%-----------------------------------------------------------------------------------------------
%Toolbox used: Symbolic Math Toolbox
%Function used in toolbox : syms
%It provides set of functions for solving ploting and manipulating symbolic  math equations
%Diff: used to find the differential and it has 2 parameters
%Disp: used to display
%input: used to take input from user
%ezplot: used to plot , fplot not compatible to octave hence not used 
%fprintf: used to print an empty line
%vpa: used to create a variable-precision floating point number (set- precision)
%-----------------------------------------------------------------------------------------------
%The program first runs according to the dimensions given.
%Then the program will ask user for the input and run accordingly
%PROGRAM STARTS:
%-----------------------------------------------------------------------------------------------
%Displaying names and student iDs of prograaming team 
disp(' i212487 Kulsoom Tariq   i210572 Kissa Zahra   i210603 Hamna Rizwan');
%Asking user to press Enter key to continue
input('Press ''Enter'' to continue...','s');
%to print an empty line
fprintf('\n') ;
%Asking user if they want to run another query or terminate ode 
%For the given data 20 by 24 inch cardboard sheet
%The equation of volume is: V=2x(12-2x)(20-2x)
disp('ASSINGMENT PART A');
%to print an empty line
fprintf('\n') ;
syms x;
y = 8*x.^3 - 128*x.^2 + 480*x.^1;
%plotting graph
ezplot(y);

ff = y;
%taking derivative 
ffd = diff(ff,x);
%displaying derivative
disp('The equation of first derivative is: '),disp(ffd);
eq=ffd;
%solving equation to find roots
s = solve(eq);
%to print an empty line
fprintf('\n') ;
%displaying roots
r1 = vpa(s(1),6);
r2 = vpa(s(2),6);
disp('The first root is: '), disp(r1);
disp('The second root is: '), disp(r2);
%to print an empty line
fprintf('\n') ;
%finding second derivative
eq1d(x)=diff(eq,x);
%displaying derivative
disp('The equation of second derivative is: '), disp(eq1d);
disp('The extrema are: ');
extrema = vpa(eq1d(s), 6);
%to make it generic
%subsitute = subs(y, x, extrema)
disp(extrema);
%to print an empty line
fprintf('\n') ;
%ezplot(y, subsitute)
disp('When x = 2.42740 is subsituted in the equation of secind derivative');
disp('The extrema being negative is hence the maxima ');
%to print an empty line
fprintf('\n') ;
%V=length*width*height
sym x1;
vol = 8*2.427.^3 - 128*2.427.^2 + 480*2.427.^1;
disp('The maximum volume is: ');
disp(vol);

fprintf('\n') ;
disp('~ PART A COMPLETED ~');
fprintf('\n') ;
fprintf('\n') ;

disp('ASSINGMENT PART B');
fprintf('\n') ;
%Finding dimensions of circular steel wire 
%to make a rectangle of maximum area
%Given data: radius = 0.5 inch
%Circumference = perimemter 
% 2*πr = 2(l+w)
r = sym(1)/2;
p = 2*((sym (pi)*r));
disp('The perimeter of the rectangle is: ');
disp(p);
fprintf('\n') ;

disp('Equating perimeter and circumference:');
syms w;
A = ((sym (pi)/2)*w.^1) - w.^2;
z = A;
Ad = diff(z, w);
disp('The equation of first derivative is: '),disp(Ad);
A1 = solve(Ad==0);
disp('The width is: ');
disp(A1);
fprintf('\n') ;

disp('Length = π/2 - w');
l = sym(pi)/2 - A1;
disp('The length is: '), disp(l);
fprintf('\n') ;

disp('Dimensions are:');
disp('π/4 by π/4');
fprintf('\n') ;

disp('For maximum area: the dimensions are equal hence it is a square');

fprintf('\n') ;
disp('~ PART B COMPLETED ~');
fprintf('\n') ;
fprintf('\n') ;

disp('ASSINGMENT PART C');
fprintf('\n') ;

disp('The cost of one cardboard is $1');
disp('The cost of one wrapping sheet is $1');
disp('One wrapping sheet covers 1 sq feet');
fprintf('\n') ;

disp('Minimising surface area:');
disp('Surface area = 2(l*w + w*h + h*l)');
%taking values of l, w and h from part a
x = 2.427;
%x is the critical point giving maximum volume
%The value by which we found length
%The value by which we found length, width, height and eventually volume 
%SA = 480 - 8*x.^2
%Dividing SA by 12^2 to convert to feet as 1/12 inch is 1 feet
SA = (480 - 8*x.^2)/(12.^2);
disp('The surface area of the box in sq feet is: '), disp(SA);
fprintf('\n') ;

disp('The total cost of wrapping sheet in dollars is :');
cWS = SA*1;
disp(cWS);
fprintf('\n') ;

disp('The total cost = cost of one cardboard + total cost of wrapping sheet');
fprintf('\n') ;
disp('The total cost of 1 juice box in dollars is: ');
cJB = cWS + 1;
disp(cJB);

fprintf('\n') ;
disp('~ PART C COMPLETED ~');
fprintf('\n') ;
fprintf('\n') ;

%Display the 3D figure
b = 7.14;  %inner square of the hollow beam for casting
l = 15.146;
h = 4.854;
x = [0 b b 0 ] %0 10 10 breadth-10 breadth-10 10];
y = [0 l];
z = [0 0 h h ] %0 10 10 breadth-10 breadth-10 10];
m = length(x);
xr=[x x(1)];
yr1=y(1)*ones(m+1,1);
zr=[z z(1)];
plot3(xr,yr1,zr,'k');
hold on
yr2=y(2)*ones(m+1,1);
plot3(xr,yr2,zr,'k');
hold on
for i=1:1:m
plot3([x(i) x(i)],y,[z(i) z(i)],'k');    
end
hold on

syms i;
    i = input('Do you want to run another query? Choose 1 to continue and 0 to terminate program)');
        
while(i==1)
    %Displaying names and student iDs of prograaming team 
    disp(' i212487 Kulsoom Tariq   i210572 Kissa Zahra   i210603 Hamna Rizwan');
    %Asking user to press Enter key to continue
    input('Press ''Enter'' to continue...','s');
    %to print an empty line
    fprintf('\n') ;
   
    var1 = input("Enter the length of the cardboard : ");
    var2 = input("Enter the width of the cardboard : ");
    
    %Now to find the dimensions of the juice box
    fprintf('\n');
    
    
    fprintf('\n');
    % V = l*w*h
   syms x;
    y = (var1*var2*x)-(2*x.^2*var1)-(4*x.^2*var2)+(8*x.^3);
    disp('The equation is: ')
    disp(y);
    ff = y;
    %taking derivative 
    ffd = diff(ff,x);
    %displaying derivative
    disp('The equation of first derivative is: '),disp(ffd);
    eq=ffd;
    %solving equation to find roots
    s = solve(eq);
    %to print an empty line
    fprintf('\n');
    %displaying roots
    
    x1 = vpa(s(1), 6);
    x2 = vpa(s(2), 6);
    
    disp('The first root is: '), disp(x1);
    disp('The second root is: '), disp(x2);
    
    
    fprintf('\n');
    %finding second derivative
    eq1d(x)=diff(eq,x);
    %displaying derivative
    disp('The equation of second derivative is: '), disp(eq1d);
    disp('The extrema are: ');
    extrema = vpa(eq1d(s), 5);
    
    disp(extrema);
    %to print an empty line
    fprintf('\n');
    
    fprintf('\n');
    disp('Maxima when x = '),disp(vpa(x1,4));
    fprintf('\n');
    fprintf('\n');
    l = (var1-4*x1)/2;
    w = (var2 - 2*x1);
    h = 2*x1;
    
    disp('Dimensions of the box: '),disp(vpa(l,4)),disp(vpa(w,4)),disp(vpa(h,4));
    fprintf('\n');
     
    disp('Maximum volume: ')
    volume = (var1*var2*x1-2*x1.^2*var1-4*x1.^2*var2+8*x1.^3);
    disp(vpa(volume,4));
    fprintf('\n'); 
    
    Area =  2*(l*w + w*h + l*h)/144;
    disp('Area in sq feet is: ');
    disp(vpa(Area,4));
    fprintf('\n');
    
    wrappingcost = Area ;
    
    disp('Minimum cost of wrapping sheet is: ');
    disp(vpa(wrappingcost,4));
    fprintf('\n');
    
    juicebox = Area + 1;
    disp('Minimum cost of juice box is: ');
    disp(vpa(juicebox,4));
    fprintf('\n');
    
    syms choice;
    i = input('Do you want to run another query?(1/0)');
    if(i != 1)
    end
end   