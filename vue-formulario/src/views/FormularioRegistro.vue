
<template>
  <div class="max-w-3xl mx-auto">
    <div v-show="paso === 1">
      <h2 class="text-xl font-bold mb-4">Paso 1: Información personal</h2>
      <div class="flex items-center mb-4">
        <label for="pais" class="w-1/4 text-center mr-1">País:</label>
        <div class="w-1/2 relative">
          <select id="pais" v-model="paisSeleccionado"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow">
            <option disabled value="">Seleccionar país</option>
            <option v-for="pais in paises" v-bind:key="pais">{{ pais }}</option>
          </select>
          <div class="absolute inset-y-0 right-0 flex items-center px-2 pointer-events-none">
            <svg v-if="paisSeleccionado" class="h-6 w-6 text-green-500" fill="currentColor" viewBox="0 0 20 20">
              <path d="M0 11l2-2 5 5L18 3l2 2L7 18z" />
            </svg>
            <svg v-else class="h-6 w-6 text-red-500" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd"
                d="M19.707 18.293L1.414 0 0 1.414l18.293 18.293L0 37.001l1.414 1.414 18.293-18.293L37.001 39l1.414-1.414L19.707 18.293z"
                clip-rule="evenodd" />
            </svg>
          </div>
        </div>
      </div>
      <div class="flex items-center mb-4">
        <label for="genero" class="w-1/4 text-center mr-1">Género:</label>
        <div class="w-1/2 relative">
          <select id="genero" v-model="generoSeleccionado"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow">
            <option disabled value="">Seleccionar género</option>
            <option value="masculino">Masculino</option>
            <option value="femenino">Femenino</option>
            <option value="otro">Otro</option>
          </select>
          <div class="absolute inset-y-0 right-0 flex items-center px-2 pointer-events-none">
            <svg v-if="generoSeleccionado" class="h-6 w-6 text-green-500" fill="currentColor" viewBox="0 0 20 20">
              <path d="M0 11l2-2 5 5L18 3l2 2L7 18z" />
            </svg>
            <svg v-else class="h-6 w-6 text-red-500" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd"
                d="M19.707 18.293L1.414 0 0 1.414l18.293 18.293L0 37.001l1.414 1.414 18.293-18.293L37.001 39l1.414-1.414L19.707 18.293z"
                clip-rule="evenodd" />
            </svg>
          </div>
        </div>
      </div>
      <div class="flex items-center mb-4">
        <label for="primer-nombre" class="w-1/4 text-center mr-1">Primer nombre:</label>
        <div class="w-1/2 relative">
          <input id="primer-nombre" v-model="primerNombre" type="text"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow"
            placeholder="Ingrese su primer nombre">
          <div class="absolute inset-y-0 right-0 flex items-center px-2 pointer-events-none">
            <svg v-if="primerNombre" class="h-6 w-6 text-green-500" fill="currentColor" viewBox="0 0 20 20">
              <path d="M0 11l2-2 5 5L18 3l2 2L7 18z" />
            </svg>
            <svg v-else class="h-6 w-6 text-red-500" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd"
                d="M19.707 18.293L1.414 0 0 1.414l18.293 18.293L0 37.001l1.414 1.414 18.293-18.293L37.001 39l1.414-1.414L19.707 18.293z"
                clip-rule="evenodd" />
            </svg>
          </div>
        </div>
      </div>

      <div class="flex items-center mb-4">
        <label for="segundo-nombre" class="w-1/4 text-center mr-1">Segundo nombre:</label>
        <div class="w-1/2 relative">
          <input id="segundo-nombre" v-model="segundoNombre" type="text"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow"
            placeholder="Ingrese su segundo nombre">
          <div class="absolute inset-y-0 right-0 flex items-center px-2 pointer-events-none">
            <svg v-if="segundoNombre" class="h-6 w-6 text-green-500" fill="currentColor" viewBox="0 0 20 20">
              <path d="M0 11l2-2 5 5L18 3l2 2L7 18z" />
            </svg>
            <svg v-else class="h-6 w-6 text-red-500" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd"
                d="M19.707 18.293L1.414 0 0 1.414l18.293 18.293L0 37.001l1.414 1.414 18.293-18.293L37.001 39l1.414-1.414L19.707 18.293z"
                clip-rule="evenodd" />
            </svg>
          </div>
        </div>
      </div>
      <div class="flex items-center mb-4">
        <label for="fechaNacimiento" class="w-1/4 text-center mr-1">Fecha de Nacimiento:</label>
        <div class="w-1/2 relative">
          <input type="date" id="fechaNacimiento" v-model="fechaNacimientoSeleccionada"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow" />
          <div class="absolute inset-y-0 right-0 flex items-center px-2 pointer-events-none">
            <svg v-if="fechaNacimientoSeleccionada" class="h-6 w-6 text-green-500" fill="currentColor"
              viewBox="0 0 20 20">
              <path d="M0 11l2-2 5 5L18 3l2 2L7 18z" />
            </svg>
            <svg v-else class="h-6 w-6 text-red-500" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd"
                d="M19.707 18.293L1.414 0 0 1.414l18.293 18.293L0 37.001l1.414 1.414 18.293-18.293L37.001 39l1.414-1.414L19.707 18.293z"
                clip-rule="evenodd" />
            </svg>
          </div>
        </div>
      </div>
      <div class="flex items-center mb-4">
        <label for="tipoDocumento" class="w-1/4 text-center mr-1">Tipo de Documento:</label>
        <div class="w-1/2 relative">
          <select id="tipoDocumento" v-model="tipoDocumentoSeleccionado"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow">
            <option disabled value="">Seleccionar tipo de documento</option>
            <option value="Cédula">Cédula</option>
            <option value="Pasaporte">Pasaporte</option>
          </select>
          <div class="absolute inset-y-0 right-0 flex items-center px-2 pointer-events-none">
            <svg v-if="tipoDocumentoSeleccionado" class="h-6 w-6 text-green-500" fill="currentColor" viewBox="0 0 20 20">
              <path d="M0 11l2-2 5 5L18 3l2 2L7 18z" />
            </svg>
            <svg v-else class="h-6 w-6 text-red-500" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd"
                d="M19.707 18.293L1.414 0 0 1.414l18.293 18.293L0 37.001l1.414 1.414 18.293-18.293L37.001 39l1.414-1.414L19.707 18.293z"
                clip-rule="evenodd" />
            </svg>
          </div>
        </div>
      </div>
      <div class="flex items-center mb-4">
        <label for="numDoc" class="w-1/4 text-center mr-1">Número de Documento:</label>
        <div class="w-1/2 relative">
          <input id="numDoc" type="number" v-model="numDoc"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow" />
          <div class="absolute inset-y-0 right-0 flex items-center px-2 pointer-events-none">
            <svg v-if="numDoc" class="h-6 w-6 text-green-500" fill="currentColor" viewBox="0 0 20 20">
              <path d="M0 11l2-2 5 5L18 3l2 2L7 18z" />
            </svg>
            <svg v-else class="h-6 w-6 text-red-500" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd"
                d="M19.707 18.293L1.414 0 0 1.414l18.293 18.293L0 37.001l1.414 1.414 18.293-18.293L37.001 39l1.414-1.414L19.707 18.293z"
                clip-rule="evenodd" />
            </svg>
          </div>
        </div>
      </div>
      <div class="flex items-center mb-4">
        <label for="foto_documento_frontal" class="w-1/4 text-center mr-1">Foto de documento frontal:</label>
        <div class="w-1/2 relative">
          <input type="file" id="foto_documento_frontal" name="foto_documento_frontal"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow" />
        </div>
      </div>
      <div class="flex items-center mb-4">
        <label for="foto_documento_trasera" class="w-1/4 text-center mr-1">Foto de documento trasera:</label>
        <div class="w-1/2 relative">
          <input type="file" id="foto_documento_trasera" name="foto_documento_trasera"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow" />
        </div>
      </div>
      <div class="flex justify-between">
        <button class="bg-blue-500 hover:bg-blue-700 text-white py-2 px-4 rounded" @click="paso = 2">Siguiente</button>
      </div>
    </div>

    <div v-show="paso === 2">
      <h2 class="text-xl font-bold mb-4">Paso 2: Información de contacto</h2>
      <div class="flex items-center mb-4">
        <label for="correo-electronico" class="w-1/4 text-center mr-1">Correo electrónico:</label>
        <div class="w-1/2 relative">
          <input id="correo-electronico" v-model="correoElectronico" type="email"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow"
            placeholder="Ingrese su correo electrónico">
        </div>
      </div>



      <div class="flex items-center mb-4">
        <label for="contrasena" class="w-1/4 text-center mr-1">Contraseña:</label>
        <div class="w-1/2 relative">
          <input id="contrasena" v-model="contrasena" type="password"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow"
            placeholder="Ingrese su contraseña">
        </div>
      </div>
      <div class="flex items-center mb-4">
        <label for="confirmacionContrasena" class="w-1/4 text-center mr-1">Confirmar contraseña:</label>
        <div class="w-1/2 relative">
          <input id="confirmacionContrasena" v-model="confirmacionContrasena" type="password"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow"
            placeholder="Ingrese su contraseña de nuevo">
        </div>
      </div>
      <div class="flex items-center mb-4">
        <label for="telefono" class="w-1/4 text-center mr-1">Teléfono:</label>
        <div class="w-1/2 relative">
          <input id="telefono" v-model="telefono" type="text"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow"
            placeholder="Ingrese su número de teléfono">
        </div>
      </div>
      <div class="flex items-center mb-4">
        <label for="celular" class="w-1/4 text-center mr-1">Celular:</label>
        <div class="w-1/2 relative">
          <input id="celular" v-model="celular" type="text"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow"
            placeholder="Ingrese su número de celular">
        </div>
      </div>
      <div class="flex justify-between">
        <button class="bg-blue-500 hover:bg-blue-700 text-white py-2 px-4 rounded" @click="paso = 1">Anterior</button>
        <button class="bg-blue-500 hover:bg-blue-700 text-white py-2 px-4 rounded" @click="paso = 3">Siguiente</button>
      </div>
    </div>

    <div v-show="paso === 3">
      <h2 class="text-xl font-bold mb-4">Paso 3: Información de dirección</h2>
      <div class="flex items-center mb-4">
        <label for="codigo-postal" class="w-1/4 text-center mr-1">Código postal:</label>
        <div class="w-1/2 relative">
          <input id="codigo-postal" v-model="codigoPostal" type="text"
            class="block appearance-none w-full py-2 px-3 pr-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500 border-gray-400 rounded shadow"
            placeholder="Ingrese su código postal">
          <div class="absolute inset-y-0 right-0 flex items-center px-2 pointer-events-none">
            <svg v-if="codigoPostal" class="h-6 w-6 text-green-500" fill="currentColor" viewBox="0 0 20 20">
              <path d="M0 11l2-2 5 5L18 3l2 2L7 18z" />
            </svg>
            <svg v-else class="h-6 w-6 text-red-500" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd"
                d="M19.707 18.293L1.414 0 0 1.414l18.293 18.293L0 37.001l1.414 1.414 18.293-18.293L37.001 39l1.414-1.414L19.707 18.293z"
                clip-rule="evenodd" />
            </svg>
          </div>
        </div>
      </div>
      <div class="flex justify-between">
        <button class="bg-blue-500 hover:bg-blue-700 text-white py-2 px-4 rounded" @click="paso = 2">Anterior</button>
        <button class="bg-blue-500 hover:bg-blue-700 text-white py-2 px-4 rounded"
          @click="submitFormulario">Enviar</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      paso: 1,
      paisSeleccionado: "",
      generoSeleccionado: "",
      fechaNacimientoSeleccionada: "",
      tipoDocumentoSeleccionado: "",
      numDoc: "",
      correo: "",
      paises: ["Colombia", "México", "Argentina", "Estados Unidos"],
      genero: "",
      primerNombre: "",
      segundoNombre: "",
      fechaNacimiento: "",
      tipoDocumento: "",
      numeroDocumento: "",
      correoElectronico: "",
      contrasena: "",
      confirmacionContrasena: "",
      telefono: "",
      celular: "",
      codigoPostal: "",

    };
  },
  methods: {
    cargarFotoDocumento(lado) {
      // Lógica para cargar la foto del documento (frente o reverso)

      // Validación de la foto del documento
      let inputFile = null;
      if (lado === 'frente') {
        inputFile = this.$refs.fotoDocumentoFrente;
      } else if (lado === 'reverso') {
        inputFile = this.$refs.fotoDocumentoReverso;
      }
      if (!inputFile.files[0]) {
        alert(`Debe seleccionar una foto del documento (${lado}).`);
        return;
      }
      const file = inputFile.files[0];
      const allowedExtensions = ["jpg", "jpeg", "png"];
      const fileExtension = file.name.split(".").pop().toLowerCase();
      if (!allowedExtensions.includes(fileExtension)) {
        alert(
          `El formato del archivo seleccionado (${fileExtension}) no es válido. Por favor, seleccione un archivo en formato ${allowedExtensions.join(", ")}.`
        );
        return;
      }

      // Si la validación es exitosa, asignamos la foto correspondiente a la propiedad correspondiente
      if (lado === 'frente') {
        this.fotoDocumentoFrente = file;
      } else if (lado === 'reverso') {
        this.fotoDocumentoReverso = file;
      }
    },
    submitFormulario() {
      // Lógica para enviar el formulario
      // Validación del correo electrónico
      if (!this.correoElectronico) {
        alert("Debe ingresar un correo electrónico.");
        return;
      }
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      if (!emailRegex.test(this.correoElectronico)) {
        alert("El correo electrónico ingresado no es válido.");
        return;
      }
      console.log({
        primerNombre: this.primerNombre,
        segundoNombre: this.segundoNombre,
        correoElectronico: this.correoElectronico,
        telefono: this.telefono,
        celular: this.celular,
        codigoPostal: this.codigoPostal,
        pais: this.paisSeleccionado,
        genero: this.generoSeleccionado,
        tipoDocumentoSeleccionado:this.tipoDocumentoSeleccionado,
        numDoc:this.numDoc,
        foto_documento_frontal:this.foto_documento_frontal,
        foto_documento_trasera:this.foto_documento_trasera,

      });
    },
  },
};
</script>```