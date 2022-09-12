# 001_data_structure

## 1. 자료구조에 대해서 설명해주시고, 생각나는 자료구조에 대해 말씀해주세요

- 자료구조는 자료를 효율적으로 저장할 수 있는 방법이고, 선형 구조와 비선형 구조로 나뉘는데, 선형 구조엔 연결 리스트, 스택, 큐, 데크가 있고, 비선형 구조에는 트리와 그래프가 있습니다.

- 연결 리스트(LinkedList) 는 헤드와 노드의 연결로 구성되어 있고, Head 에서 Node 를 가르키기 위한 Next 포인터가 있습니다. Head 에서 Node, Node 에서 다음 Node 로 가르키며 연결되어있습니다. 연결리스트의 장점은 크기가 가변적이고 삽입, 삭제가 편한 장점이 있으며, 단점으로는 Head 를 통해서만 접근이 가능하다는 것과 데이터 외에 포인터를 저장하기 위한 저장공간이 추가로 필요하다는 것 입니다.

- 스택은 LIFO(후입선출) 구조, 큐는 FIFO(선입선출) 구조를 가지고 있고, 데크는 double-ended-queue 의 준말로 처음과 끝에서 삽입과 삭제가 일어납니다.

- 트리는 나무를 뒤집어 놓은 것 처럼 생긴 모양을 가지고 있는 계층형 구조로 노드와 간선 으로 구성되어 있습니다. 트리 내에 또 다른 트리가 있는 재귀적은 구조를 가지고 있고, 데이터를 순차적으로 저장하지 않는 비선형 구조를 가지고 있지만, 최적화가 잘 안된 트리의 경우엔 연결 리스트랑 동일한 시간 복잡도를 가집니다. 데이터베이스 인덱싱에도 사용됩니다. 이진 트리는 각 노드가 2개 이하의 자식 노드를 가진 트리 입니다.

- 그래프는 정점(Vertex, 자료를 저장하려는 자료의 단위, 노드(Node)라고도 말함)과 정점을 연결하는 간선(Edge, 정점 사이를 연결하는 선으로 두 정점 쌍 (u, v)로 표현)으로 구성되어 있고, 계층이 없고 정점과 정점을 연결하기 때문에 네트워크 처럼 복잡하게 연결되어 있습니다. 정점 사이를 연결하는 간선은 방향이 있거나 없을 수 있습니다. 순회는 깊이 우선 탐색(DFS, Depth-First Search, 모든 노드를 방문하고자 할 때)과 너비 우선 탐색(BFS, Breadth-First Search, 두 노드 사이의 최단 경로 혹은 임의의 경로를 찾고 싶을 때) 2가지가 있습니다.

## 참고

- <https://yoongrammer.tistory.com/42?category=956616>
- <https://jee-young.tistory.com/31>
- <https://yoongrammer.tistory.com/68>
- <https://ko.wikipedia.org/wiki/%ED%8A%B8%EB%A6%AC_%EA%B5%AC%EC%A1%B0>
- <https://yoongrammer.tistory.com/68>
- <https://velog.io/@muchogusto/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B07-%ED%8A%B8%EB%A6%AC>
- <https://ansohxxn.github.io/algorithm/bst/#-%EC%9D%B4%EC%A7%84-%ED%83%90%EC%83%89-%ED%8A%B8%EB%A6%AC%EC%9D%98-%EC%9E%A5%EC%A0%90>
- <https://m.blog.naver.com/justkukaro/220548164184>
- <https://chanhuiseok.github.io/posts/ds-2/>
- <https://gmlwjd9405.github.io/2018/08/13/data-structure-graph.html>
- <https://gmlwjd9405.github.io/2018/08/12/data-structure-tree.html>
- <https://yoongrammer.tistory.com/85?category=956616>
