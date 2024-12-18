

### Queue

- Queue는 데이터를 FIFO 방식으로 처리하는 자료구조입니다.
- Cache 구현, 프로세스 관리, 너비 우선 탐색(BFS) 등에 주로 사용됩니다.

#### enque

- 데이터가 Queue 끝에 추가되며, 시간 복잡도는 O(1)입니다.

#### deque

- 데이터가 Queue 앞에서 제거되며, 시간 복잡도는 O(1)입니다.

<hr>

### Queue 구현 방식

- Queue는 크게 Array-Based와 List-Based 방식으로 구현됩니다.

#### Array-Based Queue

- Queue를 배열로 구현하면 enque와 dequeue 과정에서 사용하지 않는 메모리가 남을 수 있습니다. 이를 방지하기 위해 원형 큐 형태로 구현합니다.
- Queue의 크기를 초과하는 경우 배열의 크기를 동적으로 확장해야 합니다. 이 경우에도 enqueue의 연산의 시간복잡도는 O(1)입니다.


#### List-Based Queue

- enqueue 연산은 리스트의 끝에 새로운 노드를 추가하면 되고, dequeue 연산은 리스트의 첫 번째 노드를 제거하면 됩니다.
- List-Based Queue는 배열 기반의 메모리 재할당 문제를 피할 수 있습니다.

<hr>


### 원형 큐

- Queue의 끝(Rear)에 도달하면, 배열의 앞(Front)으로 돌아가 데이터를 추가하거나 제거할 수 있습니다.
- Array-Based Queue에서는 enqueue와 dequeue가 반복될수록 배열의 앞부분이 비어 있는 상태로 남게 되는데, 원형 큐에서는 이 공간을 재사용합니다.

<hr>

### Queue의 확장 및 활용

#### Deque

- 양쪽 끝에서 enqueue와 dequeue 연산이 가능합니다.

####  Priority Queue

- 우선순위에 따라 데이터를 제거합니다.

<hr>

#### Queue는 다음과 같은 상황에서 유용하게 활용됩니다.

- 프린터
- CPU 작업 스케줄링
- 캐시 구현
- 너비 우선 탐색

<hr>

Q. Array-Based Queue와 List-Based Queue의 차이점

- Array-Based Queue는 성능이 전반적으로 우수하지만, 배열 크기를 초과하는 상황에서는 확장(resize)으로 인해 성능이 저하될 수 있습니다.
- List-Based Queue는 메모리 낭비가 없지만, 연산 시마다 메모리를 할당해야 하므로 전반적인 실행 시간이 약간 느릴 수 있습니다.
- 두 방식 모두 enqueue와 dequeue의 시간복잡도는 O(1)로 동일합니다.










