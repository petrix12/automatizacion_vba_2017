# Automatización de reportes Gerencia Administración Finanzas de PDVSA Comercio y Sumnistro

## Antes de iniciar:
1. Crear proyecto en la página de [GitHub](https://github.com) con el nombre: **automatizacion_vba_2017**.
    + **Description**: Automatización de reportes de la Gerencia de Administración y Finanzas de PDVSA Comercio y Suministro del año 2016 a 2021.
    + **Public**.
2. En la ubicación raíz del proyecto en la terminal de la máquina local:
    + $ git init
    + $ git add .
    + $ git commit -m "Primer commit"
    + $ git branch -M main
    + $ git remote add origin https://github.com/petrix12/automatizacion_vba_2017.git
    + $ git push -u origin main

## Código XML **Complemento Office\Plugin AyF V1.xlam**:
```xml
<customUI xmlns="http://schemas.microsoft.com/office/2009/07/customui">
	<!--- Inicio: Cinta de Opciones -->
	<ribbon>
		<tabs>
			<!--- Cinta: Gerencia de Administración y Finanzas -->
			<tab id="C01_GerAyF" label="Ger. AyF">
				<!--- Gerencial -->
				<group id="G06_General" label="General">
					<button 
						id="cmdDdP"
						size="large"
						label="DdP"
						onAction="GenerarDdP"
						image="DdP"
						screentip="Generar Datos de Presentación"
						supertip="Genera el informe para alimentar la presentación de Presupuesto"
						getEnabled="GetEnabled"
					/>				
					<button 
						id="cmdFormatosDeSolicitud"
						size="large"
						label="F. de solicitud"
						onAction="DescargarFormatosDeSolicitud"
						imageMso="AccessNavigationOptions"
						screentip="Descargar formatos de solicitud"
						supertip="Permite descargar diversos formatos de solicitudes varias"
						getEnabled="GetEnabled"
					/>
					<button 
						id="cmdFolletoPpto"
						size="large"
						label="Folleto Ppto."
						onAction="GenerarFolletoPpto"
						image="FolletoPpto"
						screentip="Generar Folleto Presupuestario"
						supertip="Genera el Folleto Presupuestario, también llamado folleto vinotinto"
					/>					
					<button 
						id="cmdInformeGestion"
						size="large"
						label="Inf. Gestión"
						onAction="GenerarInformeGestion"
						image="IdG"
						screentip="Generar Informe de Gestión"
						supertip="Genera el Informe de Gestión de la Gerencia de Admimistración y Finanzas"
						getEnabled="GetEnabled"
					/>					
					<button 
						id="cmdRDC"
						size="large"
						label="RDC"
						onAction="GenerarPresRDC"
						image="RDC"
						screentip="Generar Presentación de RDC"
						supertip="Genera la presentación de Rendición de Cuentas"
					/>
					<button 
						id="cmdInfPptoConsolidado"
						size="large"
						label="Ppto. Consolidado"
						onAction="InfPptoConsolidado"
						image="PptoCon"
						screentip="Generar Informe del Presupuesto Consolidado"
						supertip="Genera un informe del Presupuesto Consolidado de todos los Negocios de PDVSA CyS"
						getEnabled="GetEnabled"
					/>										
				</group>
				<!--- Grupo Operaciones -->
				<group id="G02_Operaciones" label="Operaciones">
					<button 
						id="cmdSIFO"
						size="large"
						label="SIFO"
						onAction="GenerarSIFO"
						image="SIFO"
						screentip="Generar SIFO"
						supertip="Genera el informe de Sistema de Información Financiera Operacional (SIFO)"
					/>
					<button 
						id="cmdFCP"
						size="large"
						label="FCP"
						onAction="GenerarFCP"
						image="FCP"
						screentip="Generar FCP"
						supertip="Genera el informe de Flujo de Caja Presupuestario (FCP)"
					/>
					<button 
						id="cmdInfOperacional"
						size="large"
						label="Inf. Operacional"
						onAction="GenerarInfOperacional"
						image="InfOp"
						screentip="Generar Informe Operacional"
						supertip="Genera el informe de gastos de CyS discretizados por meses y trimestres"
					/>					
					<button 
						id="cmdInfExpVarOp"
						size="large"
						label="Exp. Var. Op."
						onAction="GenerarInfExpVarOp"
						image="ExplicacionesOp"
						screentip="Generar Informe de Explicaciones Operacionales"
						supertip="Genera el informe de las explicaciones de la variación del presupuesto de operaciones"
					/>					
				</group>
				<!--- Grupo OCyG -->
				<group id="G03_OCyG" label="OCyG">
					<button 
						id="cmdReporteOCyG"
						size="large"
						label="Reporte compras"
						onAction="GenerarReporteOCyG"
						image="ReporteOCyG"
						screentip="Generar reporte de OCyG"
						supertip="Genera un reporte de las compras de Otros Costos y Gastos (OCyG)"
					/>				
					<button 
						id="cmdReporteONAPRE"
						size="large"
						label="ONAPRE"
						onAction="GenerarReporteONAPRE"
						image="ONAPRE"
						screentip="Generar reporte ONAPRE"
						supertip="Genera un reporte para la Oficina Nacional de Presupuesto (ONAPRE) de las compras de OCyG"
					/>					
					<button 
						id="cmdReporteMENPET"
						size="large"
						label="MENPET"
						onAction="GenerarReporteMENPET"
						image="MENPET"
						screentip="Generar reporte MENPET"
						supertip="Genera un reporte para el Ministerio de Energía (MENPET) de las compras de Importaciones"
						getEnabled="GetEnabled"
					/>					
					<button 
						id="cmdMontarEjrOCyG"
						size="large"
						label="Montar Ejercicio"
						onAction="MontarEjrOCyG"
						image="MontarEjrOCyG"
						screentip="Mantar Ejercicio de OCyG"
						supertip="Genera un nuevo escenario de OCyG en base al precio producto y el volumen establecido"
						getEnabled="GetEnabled"
					/>					
					<button 
						id="cmdAsignaciones"
						size="large"
						label="Asignaciones"
						onAction="Asignaciones"
						image="Asignaciones"
						screentip="Asignaciones Presupuestarias"
						supertip="Permite cargar las asignaciones presupuestarias"
						getEnabled="GetEnabled"
					/>										
				</group>
				<!--- Admimistración de personal -->
				<group id="G04_AdmPersonal" label="Adm. de personal">
				</group>
				<!--- Bases de datos -->
				<group id="G07_BD_AyF" label="BD AyF">
					<button 
						id="cmdMostrarTablasAyF"
						size="large"
						label="Editar Tablas"
						onAction="MostrarTablasAyF"
						imageMso="ImportSavedImports"
						screentip="Editar tablas de BD de AyF"
						supertip="Edita las tablas de BD de la gerencia de Administración y Finanzas"
					/>
				</group>
				<!--- Utilidades -->
				<group id="G05_Utilidades" label="Utilidades">
				</group>
				<!--- Grupo Administrar -->
				<group id="G01_Administrar" label="Administrar">
					<button 
						id="cmdOcultarComplemento"
						size="normal"
						onAction="HideShowHojasPlugin"
						image="OcultarMostrar"
						screentip="Ocultar / Mostrar complemento"
						supertip="Oculta o muestra las hojas del libro asociado al plugin"
					/>
					<button 
						id="cmdGuardarComplemento"
						size="normal"
						onAction="GuardarPlugin"
						image="Guardar"
						screentip="Guardar cambios al complemento"
						supertip="Guarda los cambios realizados al libro asociado al plugin"
					/>
					<button 
						id="cmdRespaldarServidor"
						size="normal"
						onAction="BackupServidor"
						imageMso="BackupSite"
						screentip="Respaldar servidor"
						supertip="Realiza un respaldo completo del servidor en el disco duro"
					/>
					<button 
						id="cmdConfigurarPlugin"
						size="normal"
						onAction="ConfigurarPlugin"
						imageMso="AddInCommandsMenu"
						screentip="Configurar plugin"
						supertip="Permite establecer las configuración del plugin"
					/>
					<button 
						id="cmdAbrirServidor"
						size="normal"
						onAction="AbrirServidor"
						imageMso="FileOpenDatabase"
						screentip="Abrir servidor"
						supertip="Abre la carpeta en donde estan contenidos todos los archivos del servidor"
					/>					
					<checkBox 
						id="chkUsarBDServidor" 
						label="Usar BD servidor"
						onAction="UsarBDServidor"
						getPressed="CargarControl_chkUsarBDServidor"
						screentip="Usar BD del servidor" 
						supertip="Indica la base de datos a utilizar (servidor o local)"
					/>
					<button 
						id="cmdBDAyFActual"
						size="normal"
						onAction="RutaBDAyFActual"
						imageMso="Spade"
						screentip="Ruta del servidor actual"
						supertip="Muestra la ruta del servidor actual"
					/>										
					<button 
						id="cmdRutaPlugin"
						size="normal"
						onAction="RutaPlugin"
						imageMso="Diamond"
						screentip="Ruta: Plugin AyF V1.xml"
						supertip="Muestra la ruta del Plugin AyF V1"
					/>															
					<button 
						id="cmdRespaldoAdm"
						size="normal"
						onAction="RespaldoAdm"
						image="Peligro"
						screentip="PELIGRO: NO EJECUTAR"
						supertip="ADVERTENCIA: Si ejecuta este comando se pueden perder datos"
					/>					
				</group>
			</tab>
		</tabs>
	</ribbon>
	<!--- Fin: Cinta de Opciones -->
	
	<!--- Inicio: Menú emergente -->
	<contextMenus>
		<!--- Menú emergente en celdas -->
		<contextMenu idMso="ContextMenuCell">
			<menu id="SubMenu_1" label="MENÚ AyF" image="AyF">
				<menu id="SubMenuTablas" label="Insertar Tablas" imageMso="TableAutoFormat">
					<!--- Grupo General -->
					<menu id="SubMenuGeneral" label="General" image="General">
						<button
							id="cmdInsTablaEventos"
							label="Eventos"
							imageMso="E"
							onAction="InsTablaEventos"
						/>
						<button
							id="cmdInsTablaOrgNegFil"
							label="Organización/Negocios/Filiales"
							imageMso="O"
							onAction="InsTablaOrgNegFil"
						/>						
						<button
							id="cmdInsTablaTasas"
							label="Tasas"
							imageMso="T"
							onAction="InsTablaTasas"
						/>							
						<button
							id="cmdInsTablaCdA"
							label="Curvas de avance"
							image="CdA"
							onAction="InsTablaCdA"
						/>	
						<button 
							id="cmdInsTablaEstrSAP"
							label="Estructura SAP"
							image="EstructuraSAP"							
							onAction="InsTablaEstrSAP"
						/>	
						<button 
							id="cmdInsTablaGyP"
							label="Ganancias y Pérdidas"
							image="GyP"							
							onAction="InsTablaGyP"
						/>																										
						<button 
							id="cmdInsTablaBG"
							label="Balance General"
							image="BG"							
							onAction="InsTablaBG"
						/>																														
					</menu>
					<!--- Grupo OCyG -->
					<menu id="SubMenuOCyG" label="OCyG" image="OCyG">
						<button
							id="cmdInsTablaPptoOCyG"
							label="Presupuesto"
							image="Ppto"
							onAction="InsTablaPptoOCyG"
						/>					
						<button
							id="cmdInsTablaProductos"
							label="Productos"
							image="Productos"
							onAction="InsTablaProductos"
						/>	
						<button
							id="cmdInsTablaLubricantes"
							label="Lubricantes"
							image="Lubricantes"
							onAction="InsTablaLubricantes"
						/>						
						<button
							id="cmdInsTablaPrecios"
							label="Precios de productos"
							image="Precios"
							onAction="InsTablaPrecios"
						/>
						<button
							id="cmdInsTablaVolumen"
							label="Volumnes de productos"
							image="Volumen"
							onAction="InsTablaVolumen"
						/>						
						<button
							id="cmdInsTablaCICSYL"
							label="Compras CICSYL"
							image="CICSYL"
							onAction="InsTablaCICSYL"
						/>							
					</menu>
					<!--- Grupo Operaciones -->
					<menu id="SubMenuOp" label="Operaciones" image="Operaciones">
						<button
							id="cmdInsTablaCECO"
							label="CECO's"
							image="CECO"
							onAction="InsTablaCECO"
						/>
						<button
							id="cmdInsTablaClaCo"
							label="Clases de Costo"
							imageMso="C"
							onAction="InsTablaClaCo"
						/>						
						<button
							id="cmdInsTablaPptoOp"
							label="Presupuesto"
							image="Ppto"
							onAction="InsTablaPptoOp"
						/>						
					</menu>
					<!--- Grupo Inversiones -->
					<menu id="SubMenuInv" label="Inversiones" image="Inversiones">
						<button
							id="cmdInsTablaCatPres"
							label="Categorias Presupuestarias"
							imageMso="QueryCrosstab"
							onAction="InsTablaCatPres"
						/>					
						<button
							id="cmdInsTablaSubCatPres"
							label="Sub Categorias Presupuestarias"
							imageMso="RecordsFreezeColumns"
							onAction="InsTablaSubCatPres"
						/>						
					</menu>
					<!--- Grupo Adm. Personal -->
					<menu id="SubMenuPer" label="Adm. de Personal" image="Personal">
						<button
							id="cmdInsTablaFL"
							label="Fuerza Laboral"
							imageMso="ShowMembersPage"
							onAction="InsTablaFL"
						/>					
						<button
							id="cmdInsTablaGADET"
							label="GADET"
							imageMso="GroupManageTask"
							onAction="InsTablaGADET"
						/>						
						<button
							id="cmdInsTablaDirectorio"
							label="Directorio"
							image="Directorio"
							onAction="InsTablaDirectorio"
						/>				
						<button
							id="cmdInsTablaMercantil"
							label="Datos mercantiles"
							image="Banco"
							onAction="InsTablaMercantil"
						/>										
					</menu>					
				</menu>				
				<!--- Ajustar Cifras Significativas -->
				<button
					id="cmdAjustarCifrasSig"
					label="Ajustar Cifras Significativas"
					imageMso="DecimalsIncrease"
					onAction="AjustarCifrasSig"
				/>										
			</menu>
			<!--- Grupo Color de Celda -->
			<menu id="MenuColorCelda" label="Color de Celda" imageMso="ColorMenu">
				<button
					id="cmdRellenoCeldaVerde"
					label="Verde"
					imageMso="ColorGreen"
					onAction="RellenoCeldaVerde"
				/>	
				<button
					id="cmdRellenoCeldaAmarillo"
					label="Amarillo"
					imageMso="ColorYellow"
					onAction="RellenoCeldaAmarillo"
				/>		
				<button
					id="cmdRellenoCeldaRojo"
					label="Rojo"
					imageMso="ColorRed"
					onAction="RellenoCeldaRojo"
				/>
				<button
					id="cmdRellenoCeldaSinColor"
					label="Sin Color"
					imageMso="ColorWhite"
					onAction="RellenoCeldaSinColor"
				/>					
			</menu>			
		</contextMenu>
	</contextMenus>
	<!--- Fin: Menú emergente -->
</customUI>
```

## Código VBA **Complemento Office\Plugin AyF V1.xlam**: