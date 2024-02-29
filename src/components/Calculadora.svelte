<script lang="ts">

  import CalculadoraModel from "../model/CalculadoraModel";
  import Botao from "./Botao.svelte";
  import Linha from "./Linha.svelte";
  import Tela from "./Tela.svelte";
  import Historico from "./Historico.svelte";

  let historico = []; 
  let operacaoAtual = "";
  let resultado = "";
  
  let calc = new CalculadoraModel()

  const numeroDigitado = (num: string) => calc = calc.numeroDigitado(num)
  const operacaoDigitada = (op: string) => calc = calc.operacaoDigitada(op)
  const calcular = () => calc = calc.calcular()
  const pontoDigitado = () => calc = calc.pontoDigitado()
  const limpar = () => calc = calc.limpar()

</script>

<div class="calculadora"> 

    <Tela valor={calc.valor} operacao={operacaoAtual} resultado={resultado} />
    <Historico historico={historico} />

    <Linha> 
        <Botao destaque triplo texto="AC" onclick={limpar}/>
        <Botao operacao texto="/" onclick={operacaoDigitada}/>
    </Linha>

    <Linha> 
        <Botao texto="7" onclick={numeroDigitado}/>
        <Botao texto="8" onclick={numeroDigitado}/>
        <Botao texto="9" onclick={numeroDigitado}/>
        <Botao operacao texto="*" onclick={operacaoDigitada}/>
    </Linha>

    <Linha> 
        <Botao texto="4" onclick={numeroDigitado}/>
        <Botao texto="5" onclick={numeroDigitado}/>
        <Botao texto="6" onclick={numeroDigitado}/>
        <Botao operacao texto="+" onclick={operacaoDigitada}/>
    </Linha>

    <Linha> 
        <Botao texto="1" onclick={numeroDigitado}/>
        <Botao texto="2" onclick={numeroDigitado}/>
        <Botao texto="3" onclick={numeroDigitado}/>
        <Botao operacao texto="-" onclick={operacaoDigitada}/>
    </Linha>

    <Linha> 
        <Botao duplo texto="0" onclick={numeroDigitado}/>
        <Botao texto="," onclick={pontoDigitado}/>
        <Botao destaque texto="=" onclick={calcular}/>
    </Linha>
   
</div>

<style>
    .calculadora{
        background-color: var(--cor-fundo);
        height: 320px;
        width: 250px;
        padding: 10px;
        border-radius: 10px;
        display: flex;
        flex-direction: column;
    }

    .s-10 {

        font-size: 1.4rem;
    }

    .s-11 {

        font-size: 1.35rem;
    }

    .s-12 {

        font-size: 1.25rem;
    }

    .s-13 {

        font-size: 1.15rem; 
    }

    .s-14 {

        font-size: 1.07rem;
    }

    .s-15 {

        font-size: 1.0rem;
    }

    .s-16 {

        font-size: 0.93rem;
    }

    .s-17 {

        font-size: 0.87rem;
    }

    .s-18 {

        font-size: 0.83rem;
    }

    .s-19 {

        font-size: 0.78rem;
    }

    .s-20 {

        font-size: 0.74rem;
    }

    .pequena {

        font-size: 0.6rem;
    }
</style>