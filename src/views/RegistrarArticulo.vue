<template>
    <v-form v-model="valid">
        <v-container>
            <v-row>
                <!--
                <v-col cols="12" md="4">
                    <v-text-field v-model="idArticulo" :counter="10" label="Id Articulo" required></v-text-field>
                </v-col>
                -->

                <v-col cols="12" md="4">
                    <v-text-field v-model="Cod_Barras" label="Codigo de Barras" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Cod_Asociado" label="Codigo Asociado" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Id_Clasificacion" label="Id Clasificacion" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Cod_Interno" label="Codigo Interno" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Descripcion" label="Descripcion" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Descripcion_Corta" label="Descripcion Corta" required></v-text-field>
                </v-col>


                <v-col cols="12" md="4">
                    <v-text-field v-model="Cantidad_Um" label="Cantidad" required></v-text-field>
                </v-col>


                <v-col cols="12" md="4">
                    <v-text-field v-model="Id_Unidad" label="Id Unidad" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Id_Proveedor" label="Id Proveedor" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Precio_Compra" label="Precio de Compra" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Utulidad" label="Utilidad" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Precio_Venta" label="Precio de Venta" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Tipo_Articulo" label="Tipo Articulo" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Stock" label="Stock" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Stock_Min" label="Stock Minimo" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Stock_Max" label="Stock Maximo" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Iva" label="Iva" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Kit_Fecha_Ini" label="Fecha de Inicio" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Kit_Fecha_Fin" label="Fecha Final" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Articulo_Disponible" label="Articulo Disponible" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Kit" label="Kit" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Fecha_Registro" label="Fecha de Registro" required></v-text-field>
                </v-col>


                <v-col cols="12" md="4">
                    <v-text-field v-model="Visible" label="Visible" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Puntos" label="Puntos" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Last_Update_Inventory" label="Ultima Actualización" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">
                    <v-text-field v-model="Cve_Producto" label="Clave del Producto" required></v-text-field>
                </v-col>

                <v-col cols="12" md="4">

                    <v-btn depressed @click="Guardar" color="success">
                        Registrar Articulo
                    </v-btn>
                </v-col>

            </v-row>
        </v-container>
    </v-form>
</template>
<script>
export default {
    data: () => ({
        valid: false,
        Cod_Barras: '',
        Cod_Asociado: '',
        Id_Clasificacion: '',
        Cod_Interno: '',
        Descripcion: '',
        Descripcion_Corta: '',
        Cantidad_Um: '',
        Id_Unidad: '',
        Id_Proveedor: '',
        Precio_Compra: '',
        Utulidad: '',
        Precio_Venta: '',
        Tipo_Articulo: '',
        Stock: '',
        Stock_Min: '',
        Stock_Max: '',
        Iva: '',
        Kit_Fecha_Ini: new Date().toISOString(),
        Kit_Fecha_Fin: new Date().toISOString(),
        Articulo_Disponible: true,
        Kit: true,
        Fecha_Registro: new Date().toISOString(),
        Visible: true,
        Puntos: '',
        Last_Update_Inventory: new Date().toISOString(),
        Cve_Producto: '',

    }),
    methods: {
        Guardar() {
            fetch('https://localhost:44337/api/Articulos/Crear', {
                method: 'POST',
                headers:{
                    'Content-Type':'application/json'
                },
                body: JSON.stringify({
                    
                    Cod_Barras: this.Cod_Barras,
                    Cod_Asociado: this.Cod_Asociado,
                    Id_Clasificacion: parseInt(this.Id_Clasificacion),
                    Cod_Interno: this.Cod_Interno,
                    Descripcion: this.Descripcion,
                    Descripcion_Corta: this.Descripcion_Corta,
                    Cantidad_Um: parseFloat(this.Cantidad_Um),
                    Id_Unidad: this.Id_Unidad,
                    Id_Proveedor: this.Id_Proveedor,
                    Precio_Compra: parseFloat(this.Precio_Compra),
                    Utulidad: parseFloat(this.Utulidad),
                    Precio_Venta: parseFloat(this.Precio_Venta),
                    Tipo_Articulo: this.Tipo_Articulo,
                    Stock: parseInt(this.Stock),
                    Stock_Min: parseInt(this.Stock_Min),
                    Stock_Max: parseInt(this.Stock_Max),
                    Iva: parseFloat(this.Iva),
                    Kit_Fecha_Ini: this.Kit_Fecha_Ini,
                    Kit_Fecha_Fin: this.Kit_Fecha_Fin,
                    Articulo_Disponible: this.Articulo_Disponible,
                    Kit: this.Kit,
                    Fecha_Registro: this.Fecha_Registro,
                    Visible: this.Visible,
                    Puntos: parseInt(this.Puntos),
                    Last_Update_Inventory: this.Last_Update_Inventory,
                    Cve_Producto: this.Cve_Producto
                })
            }).then(res => res.text()).then(data => {
                if (data == 'Articulo insertado')
                {
                    alert("Succcess")
                }
            })
        }
    }
}
</script>