<template>
  <div class="collection">
    <div class="navbar">
      <p class="float-left">COLLECTIONS</p>
      <p class="float-right">FLOOR</p>
    </div>
    <div>
      <ul class="list-group">
        <li class="list-group-item d-flex justify-content-between align-items-center">
           <div class="list-group-item-left">
             <img class="float-left" :src="svg1">
             <div class="d-inline-block">
              <p>Azuki</p>
              <span>1 token</span>
             </div>
           </div>
          <span>
            <img :src="upsvg" />
            <p>26.5</p>
            <img style="margin-left:2px;" :src="etherium" />
          </span>
        </li>
                <li class="list-group-item d-flex justify-content-between align-items-center">
           <div class="list-group-item-left">
             <img class="float-left" :src="clonex">
             <div class="d-inline-block">
              <p>Clone X - X Takashi...</p>
              <span>1 token</span>
             </div>
           </div>
          <span>
            <img :src="upsvg" />
            <p>18.95</p>
            <img style="margin-left:2px;" :src="etherium" />
          </span>
        </li>
                <li class="list-group-item d-flex justify-content-between align-items-center">
           <div class="list-group-item-left">
             <img class="float-left" :src="beanz">
             <div class="d-inline-block">
              <p>Beanz Official</p>
              <span>1 token</span>
             </div>
           </div>
          <span>
            <img :src="down" />
            <p>12</p>
            <img style="margin-left:2px;" :src="etherium" />
          </span>
        </li>
                <li class="list-group-item d-flex justify-content-between align-items-center">
           <div class="list-group-item-left">
             <img class="float-left" :src="acrade">
             <div class="d-inline-block">
              <p>Acrade Land</p>
              <span>1 token</span>
             </div>
           </div>
          <span>
            <img :src="upsvg" />
            <p>1.03</p>
            <img style="margin-left:2px;" :src="etherium" />
          </span>
        </li>
                <li class="list-group-item d-flex justify-content-between align-items-center">
           <div class="list-group-item-left">
             <img class="float-left" :src="mutant">
             <div class="d-inline-block">
              <p>Mutant Ape Yacht C...</p>
              <span>1 token</span>
             </div>
           </div>
          <span>
            <img :src="upsvg" />
            <p>26.5</p>
            <img style="margin-left:2px;" :src="etherium" />
          </span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
           <div class="list-group-item-left">
             <img class="float-left" :src="azuma">
             <div class="d-inline-block">
              <p>Azuma Origins</p>
              <span>1 token</span>
             </div>
           </div>
          <span>
            <img :src="down" />
            <p>115</p>
            <img style="margin-left:2px;" :src="etherium" />
          </span>
        </li>
      </ul>
    </div>
    </div>
</template>
<script>
import svg1 from '../assets/list-item1.svg';
import etherium from '../assets/etherium.svg';
import upsvg from '../assets/up.svg';
import clonex from '../assets/clonex.svg';
import beanz from '../assets/beanx.svg';
import acrade from '../assets/acrade.svg';
import mutant from '../assets/mutant.svg';
import azuma from '../assets/azuma.svg';
import down from '../assets/down.svg';




export default {
    data() {
      return {
        svg1,
        etherium,
        upsvg,
        clonex,
        beanz,
        acrade,
        mutant,
        azuma,
        down

      }
    }
  };
</script>