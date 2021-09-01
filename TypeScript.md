# TypeScript

## Type Aliases(类型别名)

- `type`: 类型别名就是 任何类型的名称

  ```typescript
  type Iobj = {
    foo: string;
    bar: number;
  }
  
  let obj:Iobj = {
    foo: '123',
    bar: 123
  };
  
  type Ivar = number;
  
  let foo:Ivar = 123;
  ```

## Utility Types(实用程序类型)

- `Partial<Type>`: 构造一个`把 Type 的所有属性类型设置为可选`的类型。此实用程序将返回表示给定类型的所有子集的类型。
  
  ```typescript
  interface Todo {
    title: string;
    description: string;
  }
  
  type OptionalTodo = Partial<Todo> // { title?: string; description?: string; }
  ```
