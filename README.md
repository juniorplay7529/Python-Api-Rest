# Python-Api-Rest
Projetos relacionados ao  consumo de  Api com Python.

Com o surgimento de novas maneiras de organização dados ou formatos, permintindo transmitir de diversas formas os dados e recuperar da mesma forma. Atualmente é popular tornar-la API RESTful. 

Como fim de estudos, iremos utilizar do modulo "requests", presente no repostirio do Python, que pode ser intalado pelo pip. Usando o seguinte comando: "pip install requests".
Depois de intalado o pacote podemos testar o pacote criando um script ou utilizando o terminal interativo do python: Digite "import requests", se o pacote estiver instalado corretamente na aparecerá nenhum erro.

O módulo requests possui varios métodos, como, GET, POST, DELETE, PUT. Esses são alguns dos principais métodos, utilizados pelo protocolo de comunicação, o HTTP.

O métodos GET tem como função a obtenção de dados, para isso devemos passar um caminho no qual ele fará a busca.                          Exemplo:                                                                                                                                        import requests                                                                                                                           resp = requests.get('https://todolist.example.com/tasks/')                                                                        Na primeira linha é importado o pacote requests que permite nos permite a utilização dos métodos, como o Get que é demostrado sua utilização acima para a obteção do que buscamos.                                                                                                                                                                                                                                                                                                                                                                          O métodos DELETE tem como função a deletar dados, para isso devemos passar um caminho.                                                Exemplo:                                                                                                                                        import requests                                                                                                                           resp = requests.delete('https://todolist.example.com/tasks/<item_id>/')                                                         Na primeira linha é importado o pacote requests,e na segunda linha é utilizado o método DELETE, no qual é passado o caminho no qual ele vai ser aplicado. Os outros métodos básicos segue o mesmo modelo.                                                                                                                                                                                                                Mas que esse simples comandos não podemos ainda ver os dados "retornados", com isso segue o modelo de como poderemos melhorar nosso codigo e o retorno dos dados para visualização. No repositório possui um arquivo com o nome "ConsumindoApiPython", o qual tem a função de obter um cep válido e buscar dados básicos. Esse script pode servir de base. Obs: o usuário deve digitar o CEP a ser buscado.                                                                                                                                                                                                                            import requests

resp = requests.get('https://todolist.example.com/tasks/')
if resp.status_code != 200:
    # This means something went wrong.
    raise ApiError('GET /tasks/ {}'.format(resp.status_code))
for todo_item in resp.json():
    print('{} {}'.format(todo_item['id'], todo_item['summary']))

