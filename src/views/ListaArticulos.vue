<template>
    <v-data-table
        :headers="headers"
        :items="articulos"
        class="elevation-2"
    ></v-data-table>
</template>
<script>
export default {
    data() { 
        return {
            headers: [
                { text: 'Id del Articulo', value: 'idArticulo' },
                { text: 'Código de Barras', value: 'cod_Barras' },
                { text: 'Código de Asociado', value: 'cod_Asociado' },
                { text: 'Id Clasificacion', value: 'id_Clasificación' },
                { text: 'Codigo Interno', value: 'cod_Interno' },
                { text: 'Descripcion', value: 'descripcion' },
                { text: 'Descripcion Corta', value: 'descripcion_Corta' },
                { text: 'Cantidad', value: 'cantidad_Um' },
                { text: 'Id Uniadad', value: 'id_Unidad' },
                { text: 'Id Proveedor', value: 'id_Proveedor' },
                { text: 'Precio de Compra', value: 'precio_Compra' },
                { text: 'Utilidad', value: 'utilidad' },
                { text: 'Precio de Venta', value: 'precio_Venta' },
                { text: 'Tipo de Articulo', value: 'tipo_Articulo' },
                { text: 'Stock', value: 'stock' },
                { text: 'Stock Minimo', value: 'stock_Min' },
                { text: 'Stock Maximo', value: 'stock_Max' },
                { text: 'Fecha Inicial', value: 'kit_Fecha_Ini' },
                { text: 'Fecha Final', value: 'kit_Fecha_Fin' },
                { text: 'Kit', value: 'kit' },
                { text: 'Fecha de Registro', value: 'fecha_Registro' },
                { text: 'Visible', value: 'visible'},
                { text: 'Puntos', value: 'puntos'},
                { text: 'Ultima Actualización de Inventario', value: 'last_Update_Inventory'},
                { text: 'Clave del Producto', value: 'cve_Producto'},
        ],
            articulos: [],
            search: '',
            pagination: {},
        selected: [],
        }
    },
    created() {
        this.initialize()
    },
    methods: {
        initialize() {
            fetch('https://localhost:44337/api/Articulos/Listar')
            .then(response => response.json())
            .then(data => this.articulos = data)
        },
    }   

}
</script>