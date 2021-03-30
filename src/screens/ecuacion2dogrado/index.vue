
<template>
  <nb-container :style="{ backgroundColor: '#ffffff' }">
    <nb-header >
      <nb-left>
        <nb-button
          transparent
          :onPress="() => this.props.navigation.openDrawer()"
        >
          <nb-icon name="menu" />
        </nb-button>
      </nb-left>
      <nb-body>
        <nb-title>Ecuacion de segundo grado</nb-title>
      </nb-body>
      <nb-right />
    </nb-header>
    
    <nb-content>
       <image
          :style="{width: 150, height: 100}"
          :source="{uri: 'https://www.pngkey.com/png/detail/11-117401_math-cartoon-png-image-freeuse-stock-maths-steps.png'}"
        />
    <text class="text-color-primary" >Ecuacion segundo grado</text>
     <text></text>
    <text class="text-secondary"> a</text>
    <text-input
        :style="{height: 40, width: 100, borderColor: 'blue', borderWidth: 2}"
        v-model="a"
      />
     <text></text>
      <text class="text-secondary"> b</text>
      
    <text-input
        :style="{height: 40, width: 100, borderColor: 'blue', borderWidth: 2}"
        v-model="b"
      />
     <text></text>
      <text class="text-secondary"> c</text>

    <text-input
        :style="{height: 40, width: 100, borderColor: 'blue', borderWidth: 2}"
        v-model="c"
      />
      <text></text>
      <button
        v-bind:on-press="solucion"
        title="calcular"
        color=  #2737f8
        accessibility-label="ecu2dogrado"
    />
     <text></text>
    <text class="text-secondary"> Solucion= {{d}}</text>

    </nb-content>
  </nb-container>
</template>

<script>
    export default {
        data: function() {
            return {
                a: "",
                b: "",
                c: "",
                d: ""
            };
        },
          methods: {
        solucion: function() {
           this.d = this.EcuSolt(this.a,this.b,this.c)

        },
        EcuSolt: function(a,b,c){
          var message = ""
          var rad = Math.pow(parseInt(this.b),2)-(4*parseInt(this.a)*parseInt(this.c));
          var validchar = /([+-]?(?=\.\d|\d)(?:\d+)?(?:\.?\d*))(?:[eE]([+-]?\d+))?/;
          var validate = a.match(validchar) && b.match(validchar) && c.match(validchar)? true : false;
          if(a == 0){
            message =  "No se puede calcular"
          }else if (rad < 0){
            message =  "No existen soluciones reales"
          }else if(!validate){
            message =   "solo se permiten numeros";
          }else{
            var x1 = ((-1 * parseInt(this.b)) - Math.sqrt(rad)) / (2*parseInt(this.a))
            var x2 = ((-1 * parseInt(this.b)) + Math.sqrt(rad)) / (2*parseInt(this.a))
            
            message = `El valor de x1 es = ${x1} y el de x2 es = ${x2}`
          }
          return message

        }
      }
        
    }
    
</script>

<style>

.text-secondary{
  color:blue;
}
.text-color-primary {
  color: blue;
}
</style>

