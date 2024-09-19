<script lang="ts">
  import Socials from '@/components/Socials.svelte'
</script>

<style lang="scss">
  .texto-venta {
    padding: 20px;
    padding-bottom: 50px;
    backdrop-filter: blur(10px);
    background-color: rgba(255, 255, 255, 0.9);
    h3,
    h3 span {
      font-weight: bold;
      padding: 30px 0;
      padding: 20px 0;
    }

    p {
      padding: 10px 0;
      text-align: justify;
    }
  }
</style>

<div class="texto-venta">
  <div class="g-wrapper">
    <h3 class="g-title">Las páginas web <span class="g-color">no sirven para nada.</span></h3>

    <p>Me explico.</p>

    <p>
      Las páginas web <b>por si solas</b> no sirven para nada.
    </p>
    <p>Son un medio para comunicar un mensaje, un escaparte al mundo entero, una forma de conectar puntos.</p>
    <p>
      Por eso mismo lo que sea que ofreces tiene que ser bueno, muy bueno, algo que ayude realmente a las personas, eso es el núcleo de
      todo.
    </p>
    <p>Teniendo eso, una web bien hecha sirve para multiplicar esa esencia, llegar a más gente y dejar una huella en ellos.</p>
    <p>Pero... ¿Cómo? Haciendo que el envoltorio sea bonito, funcional, elegante y que <b> transmita el mensaje que quieres dar.</b></p>
    <p>Debo decir que personalmente me causa muchísima desconfianza investigar una empresa y ver que la web esta descuidada.</p>

    <p>
      <b>Para quedarte en medias tintas no hagas nada.</b>
    </p>

    <p>Si no, puedes provocar el efecto contrario y que tus visitantes piensen cosas estilo:</p>
    <p style="color: var(--colorText2); font-style: italic;">
      "¿Si son chapuzas con esto, lo serán para todo?"<br />"¿Quién ha decidido hacer esto y quién ha dado el visto bueno?"<br />"¿Por qué
      son tan descuidados?"
    </p>
    <br />

    <p>
      Mi vocación consiste en <b>desactivar esas preguntas</b> y que los visitantes se <b> conviertan en clientes </b> a través de una experencia
      de usuario memorable.
    </p>
    <br />
    <b>Mi receta:</b>
    <p class="g-color">Zambullirme en tu sector, una web 100% a medida, textos de venta persuasivos y un diseño acorde a tu mensaje.</p>
    <p style="font-size: 14px;">
      PD: No trabajo con Wordpress, ni con plantillas, ni con el código de otros. <br />PD2: Si crees que podemos llevarnos bien, aquí abajo
      te dejo cómo contactarme.
    </p>
  </div>

  <Socials />
</div>
