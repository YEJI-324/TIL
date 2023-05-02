# Vue Lifecycle
![vue lifecycle](../assets/vue2-lifecycle.jpg)

## Creation(생성)
생성 단계에서는 beforeCreate()와 created()가 있음.

### beforeCreate()
- 라이프사이클 중에서 가장 처음 실행.
- 컴포넌트가 DOM에 추가되기 전 ➡️ DOM 접근 불가.

### created()
- `date()` 변수, `events` 메서드 접근 가능.

## Mounting(장착)
### beforeMount()
- `<template>` 태그가 실행된 후 실행.
- 템플릿과 렌더 함수들이 컴파일된 후 첫 렌더링이 일어나기 직전에 실행.

### mounted()
- 템플릿과 렌더링된 DOM에 접근 가능.
- 부모, 자식 관계에서 컴포넌트 렌더링할 때, 자식 컴포넌트가 부모 컴포넌트보다 먼저 `mounted()` 실행.

## Updating(수정)
### beforeUpdate()
- 컴포넌트 데이터가 변하여 업데이트 시작될 때 실행.

### update()
- 컴포넌트가 데이터가 변하여 재렌더링이 일어난 후에 실행.
- DOM이 업데이트 완료된 상태 ➡️ 연산가능.

## Destrucion(소멸)
### beforeDestory()
- 뷰 컴포넌트가 제거(소멸) 되기 직전에 호출.
- 컴포넌트 기본 모습과 기능을 그대로 가지고 있음. ➡️ 이벤트리스너를 제거할 때 사용.

### destory()
- 소멸된 후에 호출.
- Vue의 모든 디렉티브 바인딩이 해제되고 모든 이벤트리스너가 제거.
- 모든 하위 Vue 컴포넌트 삭제.
