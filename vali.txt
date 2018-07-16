function validate()
{
		var ptr=1;
		var fname=document.getElementById('fname').value;
		var phNo=document.getElementById('phNo').value;
		var eid=document.getElementById('eid').value;
		var message=document.getElementById('message').value;
		checkName(fname); 
		checkPhno(phNo);
		checkEmail(eid);
		checkMsg(message);
		function checkName(name)
		{
			var l=name.length;
			if(name=="" && l<=15)
			{		
					var msg="String of 15 characters max.";
					document.getElementById('pfname').innerHTML=msg;
					ptr=0;
					//return false;
			}
			//return true;
		}
		function checkPhno(pnostr)
		{
			pNo=parseInt(pnostr);
			regPno=/^\d{10}$/;
			if(regPno.test(pNo)==0 || pNo=="")
			{
					var msg="Enter a 10-digit number";
					document.getElementById('pphNo').innerHTML=msg;
					ptr=0;
					//return false;
			}
			//return true;
		}
		function checkEmail(eid)
		{
			if (/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(eid)==0)
			{
				//alert("Please enter a valid email id!");
				var msg="Enter a valid email with @ and .com";
					document.getElementById('peid').innerHTML=msg;
					ptr=0;
				//return false;
			}
			//return true;
		}
		function checkMsg(message)
		{
		var e = document.getElementById("message");
			if(message.value == "") 
			{
				var msg="Should not be empty";
					document.getElementById('pmessage').innerHTML=msg;
					ptr=0;
				//return false;
			}
			//return true;
		}
if(ptr==1)
	{
			alert("Your Enquiry Request has been sent!!!");
			window.location.href='home.html';
		}
else{
			alert("Oops!! You have a few errors. Please correct and then proceed");	
		}
}		
		