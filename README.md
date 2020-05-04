# Tripping
this is my project
<!DOCTYPE html>
<html>
<head>
    <title>Ma Voiture</title>
    <script>
        function moteur(cylindre,puissance,carburant){
                	this.cylindre = cylindre;
                	this.puissance = puissance;
                	this.carburant = carburant;
        };        
        function voiture(marque,modele,couleur,annee,moteur,chemin) {
        	    this.marque = marque;
                this.modele = modele;
                this.couleur = couleur;
                this.annee = annee;
                this.moteur =  moteur;
                this.chemin = chemin;
        };
    </script>
    <script>
        function affichecar(voit){
           var result = "<ul><li>marque :" + voit.marque + "</li><li>modele :" + voit.modele + "</li><li>couleur :" + voit.couleur + "</li><li>annee :" + voit.annee + "</li><li>moteur :</li><ul><li>cylindre :" + voit.moteur.cylindre + "</li><li>puissance :" + voit.moteur.puissance + "</li><li>carburant :" + voit.moteur.carburant + "</li><li>chemin :" + voit.chemin + "</li></ul> </ul>";
           return result;
        };
        var moto1 = new moteur(2,8,"diesel");
        var voit1 = new voiture("volvo",300,"noir",2010,moto1,"image1.jpg");
        var moto2 = new moteur(1.5,9,"essence");
        var voit2 = new voiture("fiat",208,"bleue",2005,moto2,"image2.jpg");
        var voit3 = new voiture("nissan",300,"vert",2012,moto1,"image3.jpg");
    </script>

</head>

<body>

  <p id="nan"></p>

 <script>
   var voitures =[voit1,voit2];
   voitures.push(voit3);
     var i,t,h;
     h = voitures.length; t="<select id='select'>";

      for (i=0 ; i<h ; i++){
         t += "<option>" + "voit" +[i+1]+ "</option>";
      };

      t += "</select>";
   document.getElementById("nan").innerHTML = t;   
      
  </script>
  

  <a href="#" onclick="traiteclicbis()" style="float:left;margin-left:10px ">Valider</a>
  <a href="#" onclick="traiteclic2()" style="float:left;margin-left:10px ">Effacer</a>

  <div id="mondiv" style="float:left;"></div>

  <div id="mondiv2" style="float:left;"> </div>
   
  <script> 
      function traiteclicbis(){
        var v = document.getElementById("select");
        var n = document.getElementById("mondiv");
        var s = document.getElementById("mondiv2");
        var i ;
        for ( i=0 ; i<voiture.length ; i++){
          if (v.value=="voit"+[i+1]){
            n.innerHTML = affichecar(voitures[i]);
            break;
          };
        };
        s.innerHTML = "<img src=" + voitures[i].chemin + ">";
        s.style.marginLeft="200px";
        decalage();
      };

      function traiteclic(){
         var v = document.getElementById("select");  
         var n = document.getElementById("mondiv");
         var s = document.getElementById("mondiv2");
         var i ;
         for (i = 0 ; i < voitures.length ; i++){
             if (v.value=="voit"+[i+1]){
              n.innerHTML = affichecar(voitures[i]);}
              break;};decalage()};



        function decalage(){
      var s=document.getElementById("mondiv2");
      var n=parseInt(s.style.marginLeft)-1;
                s.style.marginLeft=((n)+"px").toString();
                if(n>0){
                  setTimeout(decalage, 50);
                };
    }
    
              
            
      

      function traiteclil2(){
          document.getElementById("mondiv").innerHTML=" ";
      };

  </script> 
</body>
</html>
