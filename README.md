# Flip - rotacione objetos

## css

O css já vem formatado com os prefixos de renderizações necessários
```
    .flip-container{
      -webkit-perspective: 1000px;
       perspective: 1000px;
      -webkit-transform-style: preserve-3d;
       transform-style: preserve-3d;
    }
    .flipper{
      -webkit-transition: 0.7s;
      -o-transition: 0.7s;
      transition: 0.7s;
      -webkit-transform-style: preserve-3d;
       transform-style: preserve-3d;
      position:relative;
    }
  
    .flip-front, .flip-back{
      -webkit-backface-visibility: hidden;
       backface-visibility: hidden;
      
    }
   
    .flip-container-active .flipper{ 
      -webkit-transform: rotateY(180deg); 
       transform: rotateY(180deg);
    }
    
    .flip-back {
       padding:20px;
       position:absolute;
       top:0;
       right:0;
       -webkit-transform: rotateY(180deg);
       transform: rotateY(180deg);
    }
```
## js
```
     $(function(){
        $.fn.extend({
          flip: function (action) {
            return this.each(function () {
              if(action=='back'){
                $(this).addClass('flip-container-active');
              }else{ 
                $(this).removeClass('flip-container-active');
              }
            });
          }
        });
      $('.flip-container').hover(function(){
        $(this).flip('back');
      });
      $('.flip-container').mouseleave(function(){
        $(this).flip('front');
      });
```
acione 

```$(this).flip('back');``` Para mostrar o back

ou

```$(this).flip('front');``` Para voltar ao front

