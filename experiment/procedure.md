### Procedure
In this experiment you will guided through the position analysis of a 4 bar RRRR Grashofian Double Rocker. Unlike a double crank, or a crank rocker, the double rocker has no crank in the sense that its input link which in this case is the link 2, CANNOT complete a full rotation and there will be a lower and upper limit for the values of theta 4. Like a crank rocker, in a double rocker, the follower, which in this case is the link 4, will also NOT rotate through a full circle, and there will be a lower and upper limit for the values of theta 4. The methods of position analysis of a Double Rocker are the same as that for a double crank or crank rocker. Using complex numbers is a popular analytical approach. The location of the coupler point can also be determined graphically. An animated description of the analytical as well as graphical methods are provided in the following links.

<p class="heading-content"> 
    <object width="900" height="700" data="./content/Cmplx_pos_ana_RRRR/index.html"></object>
</p>
<p class="heading-content"> 
     <object width="900" height="700" data="./content/Gra_pos_ana_RRRR/index.html"></object>
</p>

As with a crank rocker if we try to analytically find out the extrema of the roots of theta 4 by taking derivative of theta 4 with respect to theta 2 and setting the value to zero, it will ultimately be seen that the values are non zero and different, implying that there is a range of values of theta 4. Likewise if we examine the roots of theta 4, it will also be seen, that unlike the case with a crank rocker, real values of theta 4 will exist only for a certain range of theta 2. However the simple geometrical consideration that in the extreme configurations, the 4 bar linkage will form a triangle lets us easily find the limits both analytically and graphically. The following animations show the analytical and graphical methods. The double rocker can be both Grashofian and Non Grashofian. The Grashofian double rocker is only of one type. the non Grashofian has 3 variants. In the Grashofian double rocker, two modes of assembly are possible for a given set of link lengths, the peculiarity being that if the mechanism is assembled in one mode the configurations reached by the other mode are never achieved. Thus the complete coupler curve actually consists of two different non intersecting curves. In fact this is a trait common to Grashofian double crank and crank rocker also. However in the Non Grashofian Double Rockers, such is not the case. One mode of assembly switches to the other at some point and ultimately a single coupler curve is obtained. This will be seen in the position analysis of NonGrashofian Double Rockers.

<p class="heading-content">
  <object width="900" height="700" data="./content/Cmplx_lim_pos_ana_RRRR_Grashof_Double_Rocker/index.html"></object>
</p>

<p class="heading-content">  
   <object width="900" height="700" data="./content/Gra_lim_pos_ana_RRRR_Grashof_Double_Rocker/index.html"></object>
</p> 

### Instruments
Choose link lengths, preferably keeping them within 10 units length for easy viewing of animations. Enter them and a coupler arm length and orientation of your choice in the following applet in the designated text boxes. Link 1 represents the ground link. Press the **Enter** button to verify if your data conforms to a Grashofian Double Crank. Note that coupler arm length and orientation play no role in Grashof's criteria, but you are merely asked to enter them for use in later stages. In case you get a message stating that your data does not conform to a Grashofian Double Crank, have a re look at the summary of Grashof's criteria provided in the Introduction tab and review and re enter your data.

<label><span class="style1">Check if a linkage is a Grashofian RRRR Double Rocker mechanism </span><span class="style2"><br />
Link Length 1 (Ground) :
<input type="number" id="ground" >
<br />
Link Length 2 (Crank) :
<input type="number" id="crank" />
<br />
</span></label>
<span class="style2">
<label>Link Length 3 (Coupler) :
<input type="number" id="coupler" />
</label>
<label><br />
Link Length 4 (Follower) :
<input type="number" id="follower" />
</label>
<label><br />
Coupler Arm Length :
<input type="number" id="coupler_length" />
</label>
<label><br />
Coupler Arm Orientation (in degrees) :
<input type="number" id="coupler_angle" />
<br />
<input type="submit" id="Submit" onclick="checkGrashof()" value="Check" />
</label>
</span>
<p><label></label>
</p>
<p id="grashof_type"></p>
<p id="mechanism_type"></p>

<script type="text/javascript" src="http://code.jquery.com/jquery-1.4.2.min.js"></script>
<script>
    function checkGrashof() 
    {
    var l1 = document.getElementById("ground").value;
    var l2 = document.getElementById("crank").value;
    var l3 = document.getElementById("coupler").value;
    var l4 = document.getElementById("follower").value;
    var l5 = document.getElementById("coupler_length").value;
    var theta5 = document.getElementById("coupler_angle").value; 
	var lmin, lmax;
	lmin=10000000;
	lmax=-10000000;
	var doublerocker=-1;
	var cgFlag=false;
	if ((l1<=l2) && (l1<=l3) && (l1<=l4))
	{
		lmin=l1;
	}
	if ((l2<=l1) && (l2<=l3) && (l2<=l4))
	{
		lmin=l2;
	}
	if ((l3<=l2) && (l3<=l4) && (l3<=l1))
	{
		lmin=l3;
	}
	if ((l4<=l1) && (l4<=l2) && (l4<=l3))
	{
		lmin=l4;
	}
	if (lmin!=l3)
	{
 		cgFlag=false;
	}
	if (lmin==l3)
	{
		doublerocker=1;
	}
	if ((l1>=l2) && (l1>=l3) && (l1>=l4))
	{
		lmax=l1;
	}
	if ((l2>=l1) && (l2>=l3) && (l2>=l4))
	{
		lmax=l2;
	}
	if ((l3>=l2) && (l3>=l4) && (l3>=l1))
	{
		lmax=l3;
	}
	if ((l4>=l1) && (l4>=l2) && (l4>=l3))
	{
		lmax=l4;
	}
	var Grashof=-1;
	var p=0; var q=0
	if ((lmax==l1) && (lmin==l2)) {p=l3; q=l4;}
	if ((lmax==l1) && (lmin==l3)) {p=l2; q=l4;}
	if ((lmax==l1) && (lmin==l4)) {p=l2; q=l3;}
	if ((lmax==l2) && (lmin==l3)) {p=l1; q=l4;}
	if ((lmax==l2) && (lmin==l4)) {p=l1; q=l3;}
	if ((lmax==l2) && (lmin==l1)) {p=l3; q=l4;}
	if ((lmax==l3) && (lmin==l4)) {p=l1; q=l2;}
	if ((lmax==l3) && (lmin==l1)) {p=l2; q=l4;}
	if ((lmax==l3) && (lmin==l2)) {p=l1; q=l4;}
	if ((lmax==l4) && (lmin==l1)) {p=l3; q=l2;}
	if ((lmax==l4) && (lmin==l2)) {p=l3; q=l1;}
	if ((lmax==l4) && (lmin==l3)) {p=l1; q=l2;}
	if ( lmax*1+lmin*1 < p*1+q*1)
	{
			Grashof=1;
            document.getElementById("grashof_type").innerHTML = "Link lengths are for Grashofian linkage";
	}
	if (Grashof!=1)
	{
            document.getElementById("grashof_type").innerHTML = "Link lengths are for Non Grashofian linkage";
		cgFlag=false;
	}
	if(doublerocker==1 && Grashof==1){
            document.getElementById("mechanism_type").innerHTML = "Mechanism is a Grashofian Double Rocker";
		cgFlag=true;
	}        
	if(doublerocker!=1 || Grashof!=1){
            document.getElementById("mechanism_type").innerHTML = "Mechanism is a not a Grashofian Double Rocker";
		cgFlag=true;
	}    
	if(doublerocker!=1 && Grashof==1){
            document.getElementById("mechanism_type").innerHTML = "Mechanism is not a Grashofian Double Rocker";
		if (lmin!=l3)
		{
			   document.getElementById("mechanism_type").innerHTML += ". Coupler must be smallest for Double Rocker";
		}
		cgFlag=true;
	}    
}
</script>

Once your link lengths are validated, you are expected to find out graphically the limiting positions of the double rocker using the Drawing Board Applet which will open when you click the link below. A new browser window will open along with the applet. Since the linkage is a crank rocker, therefore the follower link will rotate between two limits of theta 4. You are required to find those limits using this applet. The applet uses screen coordinates for drawing. Hence if you are using link lengths between 1 to 10 units it is advisable (although zoom is available for the applet) to choose a scale between 100:1 to 10:1 for easy on screen use.

<img src="images/drawing-board.png" width="50%">

[Java Script Simulator](drawing-board-js/drawing-board.html)

To get an animated guidance of the graphical analysis using the applet click below:

[How to use the Drawing Board to find coupler position](drawing-board-demo.html)

Validate your answer using the applet below
<p style="text-align: center;">
 <object width="700" height="500" data="./content/GrashofRRRRDoubleRockerCouplerPositionChecker/index.html"></object>
</p>
 <p style="text-align: center;">
     <object width="700" height="500" data="./content/GrashofRRRRDoubleRockerLimitPositionChecker/index.html"></object>
</p>



