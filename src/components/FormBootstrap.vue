<template>
  <div class="container mt-3">
    <h3>Dados pessoais</h3>
    <hr>
    <b-form>
      <b-row>
        <b-col md="4" sm="12">
          <b-form-group label="Nome:" label.for="nome">
          <b-form-input
            v-model="form.nome"
            id="nome"
            placeholder="Ex: João da Silva"
          >
          </b-form-input>
        </b-form-group>
        </b-col>
        <b-col md="5" sm="12">
          <b-form-group label="Email:" label.for="email" description="Seu e-mail deve ser único">
          <b-form-input
            v-model="form.email"
            id="email"
            placeholder="joao@teste.com"
          >
          </b-form-input>
        </b-form-group>        </b-col>
        <b-col md="3" sm="12">
          <b-form-group label="Status:">
            <b-form-radio-group id="status" v-model="form.status">
              <b-form-radio value="active">Ativo</b-form-radio>
              <b-form-radio value="inactive">Inativo</b-form-radio>
            </b-form-radio-group>
          </b-form-group>
        </b-col>
      </b-row>
      <b-row>
        <b-col md="4" sm="12">
          <b-form-group label="CPF:" label.for="cpf">
          <b-form-input
            v-model="form.cpf"
            id="cpf"
            placeholder="Ex: 111.111.111-11"
          >
          </b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="3" sm="12">
          <b-form-group label="RG:" label.for="rg">
          <b-form-input
            v-model="form.rg"
            id="rg"
            placeholder="Ex: 1.111.111-1"
          >
          </b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="5" sm="12">
          <b-form-group label="Data de Nascimento:" label.for="dataDeNascimento">
          <b-form-datepicker id="dataDeNascimento" v-model="form.dataDeNascimento"></b-form-datepicker>
          </b-form-group>
        </b-col>
      </b-row>
      <hr>
      <h3>Localização</h3>
      <hr>
      <b-row>
        <b-col md="4" sm="12">
          <b-form-group label="País:" label-for="pais">
            <b-form-select id="pais" v-model="form.pais" :options="paises">
            </b-form-select>
          </b-form-group>
        </b-col>
        <b-col md="4" sm="12">
          <b-form-group label="Estado:" label-for="estado">
            <b-form-select id="estado" v-model="form.estado" :options="estados">
            </b-form-select>
          </b-form-group>
        </b-col>
        <b-col md="4" sm="12">
          <b-form-group label="Cidade:" label-for="cidade">
            <b-form-select id="cidade" v-model="form.cidade" :options="cidades">
            </b-form-select>
          </b-form-group>
        </b-col>
      </b-row>
      <hr>
      <h3>Anexos</h3>
      <hr>
      <b-row>
        <b-col md="6" sm="12">
          <b-form-file 
            @input="saveFile"
            v-model="form.file"
            placeholder="Selecione uma imagem"
          ></b-form-file>
        </b-col>
      </b-row>
    </b-form>
    <b-card class="mt-3" header="Resultado">
      <pre class="m-0" > {{ form }}</pre>
    </b-card>
  </div>
</template>

<script>
export default {
  name: 'FormBootstrap',
  data() {
    return {
      form: {
        nome: "",
        email: "",
        status: "",
        cpf: "",
        rg: "",
        dataDeNascimento: "",
        pais: null,
        estado: null,
        cidade: null,
        file: ""
      },
      paises: [
        { value: null, text: "" },
        { value: "BRA", text: "Brasil" },
        { value: "USA", text: "Estados Unidos" },
        { value: "CAN", text: "Canadá" },
        { value: "USS", text: "União Soviética (Inativo)", disabled: true }
      ],
      estados: [
        { value: null, text: "" },
        { value: "PR", text: "Paraná" },
        { value: "SC", text: "Santa Catariana" },
        { value: "RS", text: "Rio Grande do Sul" }
      ],
      cidades: [
        { value: null, text: "" },
        { value: "CWB", text: "Curitiba" },
        { value: "FLN", text: "Florianópolis" },
        { value: "POA", text: "Porto Alegre" }
      ]
    }
  },
  methods: {
    saveFile(event) {
      console.log(event);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
