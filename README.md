Tabla (Grid)
=====

Muestra los valores de un origen de datos en una tabla donde cada columna representa un campo y cada fila representa un registro. La Tabla (Grid) permite seleccionar, ordenar y editar estos elementos. 

Ejemplo:
<div class="bs-docs-example">
                <table class="table table-condensed">
                    <thead>
                        <tr>
                            <th>#</th>
                            <th>First Name</th>
                            <th>Last Name</th>
                            <th>Username</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>1</td>
                            <td>Mark</td>
                            <td>Otto</td>
                            <td>@mdo</td>
                        </tr>
                        <tr>
                            <td>2</td>
                            <td>Jacob</td>
                            <td>Thornton</td>
                            <td>@fat</td>
                        </tr>
                        <tr>
                            <td>3</td>
                            <td colspan="2">Larry the Bird</td>
                            <td>@twitter</td>
                        </tr>
                    </tbody>
                </table>
            </div>

<h3> Estructura de Archivo </h3>

<pre>
&lt;!DOCTYPE html&gt; 
&lt;html&gt; 
&lt;head&gt; 
	&lt;title&gt;Ejemplo&lt;/title&gt; 
	&lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
	&lt;!-- Bootstrap --&gt; 
	&lt;link href="css/bootstrap.css" rel="stylesheet" media="screen"&gt;
	
&lt;/head&gt; 

&lt;body&gt; 
	&lt;!-- Agregar Definicion tabla aqui  ver seccion 1--&gt; 
	&lt;script src="js/jquery.js"&gt;&lt;/script&gt;
	&lt;script src="js/bootstrap.js"&gt;&lt;/script&gt; 
	&lt;script src="js/tabla.js"&gt;&lt;/script&gt;
	&lt;!-- Agregar JS de LLenado de la tabla con Jquery ver seccion 2 --&gt;
&lt;/body&gt;
&lt;/html&gt; 
</pre>

<h3> 1. Definición </h3>


Definir el objeto con su respectivo id.
<hr>
<pre>
&lt;div class="form-search pull-right" data-tabla="gvBuscar"&gt;
    &lt;input type="text" class="search-query form-control" placeholder="Buscar" /&gt;
&lt;/div&gt;
&lt;div class="table-responsive"&gt;
	&lt;table class="table table-striped table-bordered table-hover tabla" 
                data-orden="true" data-filtro="true"
            id="gvBuscar"&gt;
            &lt;caption&gt;
                Listado de blogs existentes&lt;/caption&gt;
            &lt;thead&gt;
                &lt;tr&gt;
                    &lt;th data-tipo="int" data-campo="Codigo" data-alineacion="centro"&gt;#
                    &lt;/th&gt;
                    &lt;th data-tipo="string" data-campo="Nombre"&gt;Tipo
                    &lt;/th&gt;
                    &lt;th data-tipo="datetime" data-campo="Fecha" data-formato="dddd dd/MM/yyyy HH:mm" data-alineacion="centro"&gt;Fecha Creación
                    &lt;/th&gt;
                    &lt;th data-tipo="int" data-campo="Precio" data-formato="#,##0" data-alineacion="derecha"&gt;Enteros
                    &lt;/th&gt;
                    &lt;th data-tipo="decimal" data-campo="Precio" data-formato="#,##0.00" data-alineacion="derecha"&gt;Decimales
                    &lt;/th&gt;
                    &lt;th data-tipo="foto" data-campo="Foto"&gt;Fotografía&lt;/th&gt;
                    &lt;th data-tipo="bool" data-campo="Habilitado" data-alineacion="centro"&gt;Estado
                    &lt;/th&gt;
                    &lt;th data-tipo="bool" data-campo="Status"&gt;Estado&lt;/th&gt;
                    &lt;th data-boton="Notas"&gt;asdfasdf&lt;/th&gt;
                    &lt;th data-boton="editar" data-alineacion="centro">&lt;/th&gt;
                    &lt;th data-boton="borrar" data-alineacion="centro">&lt;/th&gt;
                &lt;/tr&gt;
            &lt;/thead&gt;
            &lt;tbody&gt;
            &lt;/tbody&gt;
        &lt;/table&gt;
&lt;/div&gt;
&lt;div class="pagination"&gt;
&lt;ul class="pagination pagination-centered" data-tabla="gvBuscar" data-cantidad="10" data-grupo="8"&gt;&lt;/ul&gt;
&lt;/div&gt;

</pre>
<h3> 2.) LLenado de la tabla con Jquery </h3>
Agregar el código despues del &lt;/Form&gt; luego de la llamada de jquery.
<h4> Asp .Net </h4>
<pre>
&lt;script src="js/jquery.js"&gt;&lt;/script&gt;
&lt;script src="js/bootstrap.js"&gt;&lt;/script&gt;
&lt;script src="js/tabla.js"&gt;&lt;/script&gt;
 &lt;script type="text/javascript"&gt;
        $(document).ready(function () {
             $("#gvBuscar").tabla("pagina.aspx/llenar", null);
         });
&lt;/script&gt
</pre>
<h4> PHP Codeigniter</h4>
<pre>
&lt;script src="js/jquery.js"&gt;&lt;/script&gt;
&lt;script src="js/bootstrap.js"&gt;&lt;/script&gt;
&lt;script src="js/tablaphp.js"&gt;&lt;/script&gt;
&lt;script type="text/javascript"&gt;
        $(document).ready(function()
		{
			var base = '&lt;?php echo base_url();?&gt;';
			$('#gvBuscar').tabla(base + 'controller/lista', null);
		});
&lt;/script&gt
</pre>
<h4> Asp .Net MVC 4,5 </h4>
<pre>
@section Scripts { 
    @Scripts.Render("~/bundles/jqueryval") 
&lt;script src="js/tabla3.js"&gt;&lt;/script&gt;
    &lt;script&gt;
        $(document).ready(function () { 
            $("#gvBuscar").tabla('@Url.Action("controller", "lista")', null);
        }); 
    &lt;/script&gt;
}
</pre>
