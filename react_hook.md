리액트의 **훅(Hook)**은 함수형 컴포넌트에서 상태(state)와 생명주기(lifecycle) 기능을 사용할 수 있게 해주는 기능입니다. 클래스형 컴포넌트에서만 가능했던 기능을 함수형 컴포넌트에서도 간편하게 구현할 수 있도록 도와줍니다. 훅은 리액트 16.8 버전부터 도입되었으며, 코드의 재사용성과 가독성을 크게 향상시킵니다.

---

### **주요 훅의 종류와 설명**

1. **useState**  
   - 상태(state)를 관리하는 훅입니다.  
   - 예시:
     ```javascript
     const [count, setCount] = useState(0);
     ```
   - `count`는 현재 상태 값, `setCount`는 상태를 업데이트하는 함수입니다.

2. **useEffect**  
   - 컴포넌트의 생명주기(lifecycle)를 관리하는 훅입니다.  
   - 컴포넌트가 마운트, 업데이트, 언마운트될 때 특정 작업을 수행할 수 있습니다.  
   - 예시:
     ```javascript
     useEffect(() => {
       console.log('Component mounted or updated');
       return () => {
         console.log('Component will unmount');
       };
     }, []);
     ```

3. **useContext**  
   - 컨텍스트(Context)를 사용하여 전역 상태를 관리하는 훅입니다.  
   - 예시:
     ```javascript
     const value = useContext(MyContext);
     ```

4. **useReducer**  
   - 복잡한 상태 로직을 관리하는 훅입니다. `useState`의 대안으로 사용됩니다.  
   - 예시:
     ```javascript
     const [state, dispatch] = useReducer(reducer, initialState);
     ```

5. **useCallback**  
   - 메모이제이션된 콜백 함수를 반환하는 훅입니다. 성능 최적화에 유용합니다.  
   - 예시:
     ```javascript
     const memoizedCallback = useCallback(() => {
       doSomething(a, b);
     }, [a, b]);
     ```

6. **useMemo**  
   - 메모이제이션된 값을 반환하는 훅입니다. 계산 비용이 높은 작업에 사용됩니다.  
   - 예시:
     ```javascript
     const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
     ```

7. **useRef**  
   - DOM 요소나 변경 가능한 값을 참조하는 훅입니다.  
   - 예시:
     ```javascript
     const inputRef = useRef(null);
     ```

---

### **훅의 장점**
1. **코드 간결성**  
   - 클래스형 컴포넌트보다 코드가 간결하고 이해하기 쉽습니다.  
2. **재사용성**  
   - 커스텀 훅을 만들어 로직을 재사용할 수 있습니다.  
3. **성능 최적화**  
   - `useCallback`, `useMemo` 등을 통해 불필요한 렌더링을 방지할 수 있습니다.  

---

### **훅 사용 시 주의사항**
1. **최상위에서만 호출**  
   - 훅은 반복문, 조건문, 중첩 함수 내에서 호출하면 안 됩니다.  
2. **함수형 컴포넌트에서만 사용**  
   - 클래스형 컴포넌트에서는 훅을 사용할 수 없습니다.  

---

### **예시: 간단한 훅 사용 예제**
```javascript
import React, { useState, useEffect } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Count: ${count}`;
  }, [count]);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}

export default Counter;
```

---
