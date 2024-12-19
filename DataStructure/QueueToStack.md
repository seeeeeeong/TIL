### Queue 두 개를 이용하여 Stack을 구현해 보세요.

- Stack은 LIFO 방식으로 동작하며, 큐는 FIFO 방식으로 동작합니다. 따라서 Queue의 FIFO 동작을 활용하여 Stack의 LIFO 동작을 구현할 수 있습니다.

### 구현 아이디어

#### 1. push()

- 데이터를 입력 받아 q1에 저장합니다.

#### 2. pop()

- q1의 모든 데이터 중 마지막 데이터만 남길 때 까지 q2로 옮깁니다.
- q1에 남아있는 마지막 데이터를 반환합니다.
- q1과 q2를 swap하여 다음 작업을 진행합니다.
  코드


	public StackQ() {
		q1 = new LinkedList<>();
		q2 = new LinkedList<>();
	}
	
	public void push(int a) {
		q1.offer(a);
	}
	
	public int pop() {
		int result=-1;
		
		if(q1.isEmpty()) {
			return -1;
		}
		
		while(q1size() != 1) {
			q2.offer(q1.poll());
		}
		result = q1.poll();
		
		if(!q2.isEmpty()) {
			while(!q2.isEmpty()) {
				q1.offer(q2.poll());
			}
		}
		
		return result;
	}



### 시간 복잡도

- push() : 단순히 q1에 데이터를 삽입하므로 O(1)입니다.
- pop() : q1의 모든 데이터를 q2로 옮기는 작업이 포함되므로 O(n)입니다.
