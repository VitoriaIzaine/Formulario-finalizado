<template>
  <div class="tudo">
    <div class="container">
      <div class="titulo">
        <h1>Itens de Avaliação</h1>
      </div>

      <div
        class="form"
        v-for="(question, index) in this.questions"
        :key="index"
      >
        <div class="titulo1">
          <h1>{{ index + 1 }}. {{ question.topic }}</h1>
        </div>
        <main class="pergunta1">
          <section class="right-1">
            <div class="pg1">
              <h6 id="txUm">Nível de importância:</h6>
              <div class="rbt_importancia" id="v-model-radiobutton">
                <input
                  type="radio"
                  :id="'import-one-' + index"
                  :value="'import-one-' + index"
                  :v-model="this.picked1"
                />
                <label :for="'import-one-' + index">Alta</label>
                <br />
                <input
                  type="radio"
                  :id="'import-two-' + index"
                  :value="'import-two-' + index"  
                  :v-model="this.picked2"
                />
                <label :for="'import-two-' + index">Media</label>
                <br />
                <input
                  type="radio"
                  :id="'import-three-' + index"
                  :value="'import-three-' + index"  
                  :v-model="this.picked3"
                />
                <label :for="'import-three-' + index">Baixa</label>
              </div>
            </div>
          </section>

          <section class="left-1">
            <div class="pg1">
              <h6 id="txdois">Nível de satisfação:</h6>
              <div class="rbt_satis" id="v-model-radiobutton">
                <div class="ruim">
                  <input
                    type="radio"
                    :id="'satisf-one-' + index"
                    :value="'satisf-one-' + index"                    
                  />
                  <label :for="'satisf-one-' + index">Otimo</label>
                  <br />
                  <input
                    type="radio"
                    :id="'satisf-two-' + index"
                    :value="'satisf-two-' + index"                    
                  />
                  <label :for="'satisf-two-' + index">Bom</label>
                  <br />
                  <input
                    type="radio"
                    :id="'satisf-three-' + index"
                    :value="'satisf-three-' + index"                    
                  />
                  <label :for="'satisf-three-' + index">Não se aplica</label>
                  <br />
                </div>

                <div class="ruim">
                  <input
                    type="radio"
                    :id="'satisf-four-' + index"
                    :value="'satisf-four-' + index"                    
                  />
                  <label :for="'satisf-four-' + index">Regular</label>
                  <br />
                  <input
                    type="radio"
                    :id="'satisf-five-' + index"
                    :value="'satisf-five-' + index"                    
                  />
                  <label :for="'satisf-five-' + index">Ruim</label>
                </div>
              </div>
            </div>
          </section>
        </main>
        <div class="divisor"></div>
      </div>

      <!-- FIM PERGUNTA 1 -->
    </div>

    <div class="buttons">
      <button type="button" class="btn-send">Enviar</button>
      <button type="button" class="btn-clean">Limpar</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",

  data() {
    return {
      picked1: false,
      picked2: false,
      picked3: false,
      questions: [
        { topic: "Limpeza e conservação da sala de aula e da oficina" },
        {
          topic:
            "Disponibilidade de equipamentos, máquinas e ferramentas para a realização do curso",
        },
        {
          topic:
            "Qualidade de apostilas, livros e textos, quanto a impressão e a adequação da informação",
        },
        { topic: "Cumprimento do horário das aulas" },
        { topic: "Cumprimento dos objetivos propostos pelo curso" },
        { topic: "Preocupação do docente com o aproveitamento dos alunos" },
        { topic: "Domínio do docente sobre os assuntos tratados" },
        {
          topic:
            "O aprendizado, na teoria e na prática, em relação ao esperado",
        },
        { topic: "Conteúdo do curso, em relação às expectativas" },
        { topic: "Atendimento da recepção / secretaria da escola" },
        { topic: "Atendimento telefônico da escola" },
        { topic: "Atendimento da cantina / lanchonete" },
        { topic: "Atendimento da Biblioteca" },
      ],
    };
  },
  methods: {
    printer(element) {
      console.log(element);
    },
  },
};
</script>

<style lang="scss">
@import "./scss/home.scss";
</style>
