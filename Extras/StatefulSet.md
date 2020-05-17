## StatefulSets

Os StatefulSets são utilizados quando temos uma aplicação distribuída e precisamos manter os estados. 


Como um deployment o StatefulSet gerencia os pods baseados no spec de container, já ao contrario do Deployment o StatefulSet sempre persiste a identidade de seus pods ex:

Deployment:
```
meu-nginx-654cf8945f-vqjnb
meu-nginx-654cf8945f-58qk6
```

StatefulSet:
```
meu-nginx-0
meu-nginx-1
```

Se fizermos qualquer alteração em um deployment os nomes dos pods serão alterados, já no StatefulSet os nomes sempre serão os mesmos seguindo uma sequência numérica {0,1,2,3}.
Isso soluciona quando temos a necessidade de manter o nome de um pod,por exemplo de um cluster mysql onde os nós devem ter sempre o mesmo nome.

Você também pode utilizar volumes persistentes no StatefulSets para evitar a perda de dados

## Vantagens:

Utilizar volumes persistentes para todas replicas.
Hostname e registros DNS são mantidos os mesmos somente atualizando o ip do registro.
Dimensionamento de réplicas utilizando ordem de start e padrão de nomes.
