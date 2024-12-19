

### Stack 두 개를 이용하여 Queue를 구현해 보세요.

- 한 Stack(instack)을 데이터 입력 용도로 사용하고, 다른 Stack(outstack)을 데이터 출력 용도로 사용하여, Stack의 LIFO 특성을 FIFO로 바꾸는 것입니다.

<hr>

### 구현 아이디어

#### 1. enqueue

- 데이터를 입력 받아 instack에 추가합니다.

#### 2. dequeue

- 데이터 출력 시 outstack이 비어 있다면, instack의 데이터를 모두 pop() 하여 outstack으로 이동시킵니다.
- 이렇게 하면 가장 먼저 입력된 데이터가 outstack의 맨 위에 위치하게 됩니다.
- 그런 다음 outstack.pop()으로 데이터를 제거합니다.

<hr>

### 코드

    public Qstack() {
        instack = new Stack<>();
        outstack = new Stack<>();
    }

    // 데이터 삽입 (enqueue)
    public void enqueue(int value) {
        instack.push(value);
    }

    // 데이터 제거 (dequeue)
    public int dequeue() {
        if (outstack.isEmpty()) {
            while (!instack.isEmpty()) {
                outstack.push(instack.pop());
            }
        }

        if (!outstack.isEmpty()) {
            return outstack.pop();
        }
        throw new IllegalStateException("Queue is empty!");
    }

    public boolean isEmpty() {
        return instack.isEmpty() && outstack.isEmpty();
    }

    public int size() {
        return instack.size() + outstack.size();
    }


<hr>

### 시간 복잡도

- enqueue() : O(1)
- dequeue() : O(1), 최악의 경우 O(n) (데이터 이동 발생 시)
