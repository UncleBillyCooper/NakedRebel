<script>
</script>

<template>
 <div class="box-title">
  <h1>Доброволец!</h1>
  
  <p>Добро пожаловать в небольшой онлайн сервис,
     в котором ты можешь выбрать для своей униформы подходящий
      оттенок джинвула из ассортимента магазина Бена Тарта.
       Представленные материалы это не подбор расцветок вручную. Это фотографии джинвула, 
       полученые посредством парсинга сайта уважаемого производителя. Если приглядеться, то на отдельных участах
        можно увидеть даже монетки, которые мистер Тарт заботливо кладет на ткань для фото.</p>
   
   <p>Так что не переживай за законность, ибо ВСЕ АБСОЛЮТНО НЕЗАКОННО! Дядя Билли позаботился.</p>
   <br>
   <h3>ПЕРЕД ИСПОЛЬЗОВАНИЕМ ПРОЧТИ ПРАВИЛА, чтобы не тыкать как дурак не понятно куда, а потом материть воздух</h3>
   <p>1. В перечне расцветок (слева на основаном экране) кликни на понравившуюся расцветку.
    P.S. Там, кстати, можно перелистывать блоки карточек, если нажимать зеленые кнопки.
   </p>
   <p>2. Затем кликни на жакет или штаны, чтобы присвоить вещи цвет (шляпе цвет присваивать нельзя)</p>
   <p>3. Чтобы изменить, выбор начни заново с п. 1</p>
   <p>4. Если цвет не присваивается, значит мистер Тарт что-то изменил. Например товара больше нет. 
    Прими, как факт, что это исключительно тренировочный проект, а не коммерческий, так что обижаться не на кого
   </p>
   <br>
   <h3>ЕСЛИ ПРОЧЕЛ ПРАВИЛА, ЖМИ КНОПКУ</h3>
   <img src="../assets/finger.png" alt="">
 </div>
</template>

<style scoped>

@font-face {
 font-family: myPlaybill;
 src: url(../fonts/playbillbtcyr.ttf);
}

@font-face {
 font-family: myKellySlab;
 src: url(../fonts/kelly-slab_[allfont.ru].ttf);
}

.box-title{
 display: flex;
 flex-direction: column;
 justify-content: space-around;
 
 width: 100%;
 height: 70vh;

 text-align: center;
 padding: 20px;
 
}

img{
 display: inline-block;
 
 width: calc(3 * (1vw + 1vh));
 height: calc(3 * (1vw + 1vh));;
 align-self: center;
}

p {
 font-family: 'myKellySlab';
 /*font-size: calc(1.5vw + 1.5vh);*/
 font-size: clamp(10px, calc(0.7vw + 0.7vh), 40px);
}
h1,h3{
 font-family: 'myPlaybill';
 letter-spacing: 1px;
 font-weight: 400;
}

h1{
 font-size: calc(3 * (1vw + 1vh));
 
}

h3{
 font-size: calc(1.5 * (1vw + 1vh));
 /*font-size: 30px;*/
}
</style>
