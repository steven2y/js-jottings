# this

WIP
function Testa(a,b,c){
  this.a = a;
  this.b = b;
  this.c = c;
}

Testa.prototype.blurb = function(){
  console.log(this.a,this.b,this.c);
}


function Testb(a,b,c,d,e){
  this.d = d;
  this.e = e;
  Testa.call(this, a,b,c);
}

Testb.prototype = new Testa();
Testb.prototype.constructor = Testb;


var help = new Testb(1,2,3,4,5);
console.log(help);
console.log(help instanceof Testb,'s');
console.log(help instanceof Testa, 't');
console.log(typeof help, 't');

//console.log(help);
help.blurb();
