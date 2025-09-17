PRINCIPAL SUPORTE AOS ARQUIVOS XFBIN/XPS

SCRIPT COM A PRINCIPAL FUNÇÃO DE SUBSTITUIR DE FORMA RAPIDA MATERIAIS QUE NÃO PODEM SER EXPORTADOS PELO BLENDER

🔹 Parte 1 – Salvar texturas como PNG

O que faz:
Percorre todas as imagens carregadas no projeto Blender e salva cópias delas em formato PNG em uma pasta específica.

Conceitos de programação usados:

Funções (def save_xps_textures_as_png)

Estruturas de repetição (for image in bpy.data.images)

Condições (if image.is_dirty or not image.filepath)

Manipulação de arquivos e diretórios (os.makedirs, os.path.join)

🔹 Parte 2 – Substituir texturas nos materiais

O que faz:
Percorre todos os materiais e substitui as texturas antigas pelas versões em PNG geradas na parte 1.

Conceitos de programação usados:

Condições aninhadas (if not material.use_nodes, if node.type == 'TEX_IMAGE')

Laços de repetição sobre coleções (for material in bpy.data.materials, for node in material.node_tree.nodes)

Manipulação de caminhos e arquivos (os.path.exists)

Tratamento de exceções (try/except)

🔹 Parte 3 – Exportar texturas dos materiais

O que faz:
Percorre todos os objetos do tipo MESH, lista seus materiais e texturas, cria novos materiais baseados nas texturas encontradas e aplica novamente na malha.

Conceitos de programação usados:

Iteração sobre objetos e materiais (for obj in bpy.data.objects)

Estruturas condicionais (if obj.type == "MESH", if node.type == "TEX_IMAGE")

Criação dinâmica de objetos (bpy.data.materials.new)

Organização de saída no console (print)
