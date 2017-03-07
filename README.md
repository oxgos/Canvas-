# Canvas-
<script>
		var canvas=document.getElementById("canvas");
		var ctx=canvas.getContext("2d");
		var STATUS=0;
		var VISIBLE=1;
		var a=1;
		var img=new Image();
		img.src="bg.jpg";
		var r=Math.random()*41+10;
		var x=Math.random()*291;
		x+r>300 && (x=300-r);
		x-r<0 && (x=r);
		var y=-r;
		setInterval(function(){
			if(y+r>400){
				y=400-r;
				STATUS=1;
			}else if(y-r<0){
				y=r;
				STATUS=0;
			}
			if(a<0){
				VISIBLE=0;
				a=0;
			}else if(a>1){
				a=1;
				VISIBLE=1;
			}
			ctx.drawImage(img,0,0,300,400);
			ctx.fillStyle="rgba(250,0,0,"+a+")";
			ctx.beginPath();
			ctx.arc(x,y,r,0,Math.PI*2);
			ctx.fill();
			if(STATUS==0){
				y+=3;
			}else if(STATUS==1){
				y=y-3;
			}
			if(VISIBLE==1){
				a=a-0.01;
			}else if(VISIBLE==0){
				a+=0.01;
			}
		},50);
	</script>
canvas
