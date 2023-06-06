<template>
  <TotalCounter />
  <GameBoard />
</template>



<script>
import TotalCounter from './components/TotalCounter.vue'
import GameBoard from './components/GameBoard.vue'

export default {
  name: 'BombFlip',
  components: {
    TotalCounter, GameBoard
  }
}
</script>



<style>
:root {
    --acento:#1A6D8D;
    --acento-hover:#2589b1;
    --acento-focus:#145874;
    --secundario:#F2F2F2;
    --tablero-color:#bbada0;
    --casilla-color:rgba(238, 228, 218, 0.35);
    --casilla-hover-color:#eee4da;
    --casilla-focus-color:#026ce6;
    --casilla-info-color:#9e9184;
    --fuente-color:#696159;
    --fuente-sub-color:#887d72;
    --fuente: Clear Sans, sans-serif;
    --fuente-casilla:52px;


    --rounding: 10px;
    --width-casilla:85.65px;
    --height-casilla:85.65px;

    --columnCount:5;
    --rowCount:5;
    --grid-gap:15px;

    --total-width-table : calc(( var(--width-casilla ) * var( --columnCount )) + (var(--grid-gap )* (var(--columnCount ) -1 ))) ;
    --total-height-table : calc(( var(--height-casilla ) * var( --rowCount)) + (var(--grid-gap )* (var(--rowCount ) -1))) ;
    
    --acierto:rgba(219, 251, 228, 0.774);
    --fallo:#f56c6c;
    --ganado:#f3d779;
    /* #f77c5f */
    --pantalla-fin-juego:rgba(238,228,218,.73);
}

*{
    margin: 0;
    padding: 0;
}

body{
    background-color: var(--secundario);
}


@keyframes flipInitialCell{
    0% {
        transform: rotateY(0deg);
    }

    100%{
        transform: rotateY(360deg);
    }
}


@keyframes showErrorMsg{
    0% {
        opacity:0%;
    }

    100% {
        opacity: 100%;
    }
}



@keyframes flipCell{
    0% {
        transform: rotateY(180deg);
    }

    100%{
        transform: rotateY(0deg);
    }
}


@keyframes revealCellNumber{
    0%{
        opacity: 0;
    }
    20%{
        opacity: 0;
    }
    75%{
        opacity: .75;
        visibility: visible;
    }
    100%{
        opacity: 1;
        visibility: visible;
    }
}


@keyframes shakeAnimation{
    0% { transform: translate(1px, 1px) rotate(0deg); }
    10% { transform: translate(-1px, -2px) rotate(-1deg); }
    20% { transform: translate(-3px, 0px) rotate(1deg); }
    30% { transform: translate(3px, 2px) rotate(0deg); }
    40% { transform: translate(1px, -1px) rotate(1deg); }
    50% { transform: translate(-1px, 2px) rotate(-1deg); }
    60% { transform: translate(-3px, 1px) rotate(0deg); }
    70% { transform: translate(3px, 1px) rotate(-1deg); }
    80% { transform: translate(-1px, -1px) rotate(1deg); }
    90% { transform: translate(1px, 2px) rotate(0deg); }
    100% { transform: translate(1px, -2px) rotate(-1deg); }
}
</style>
