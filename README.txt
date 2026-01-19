Dashboard com Firebase (Firestore) - Instrucoes

Arquivos
- index.html (menu)
- cadastro.html (formulario para cadastrar e salvar no Firestore)
- sinistros.html (le do Firestore: colecao 'sinistros')
- seguro-carga.html (le do Firestore: colecao 'seguros')
- custo-gr.html (le do Firestore: colecao 'custo_gr')

1) Firebase Console
   - Abra o projeto: dashboard-gr-adm
   - Ative o Firestore Database

2) Regras (teste rapido)
   ATENCAO: isso deixa leitura/escrita aberta. Use somente para testes.

   rules_version = '2';
   service cloud.firestore {
     match /databases/{database}/documents {
       match /{document=**} {
         allow read, write: if true;
       }
     }
   }

3) Rodar o painel
   Importante: Firebase (modules) normalmente nao funciona bem abrindo o HTML direto por file://.
   Use uma destas opcoes:
   - Firebase Hosting (recomendado)
   - Ou um servidor local (ex: extensao Live Server do VS Code)

4) Como cadastrar
   - Abra cadastro.html
   - Selecione o tipo (Sinistros / Seguro / Custo GR)
   - Preencha e clique em Salvar
   - Depois abra os paineis e os dados vao aparecer automaticamente.

Dica
- Para manter performance, se sua base crescer muito, vale paginar/filtrar no Firestore.
