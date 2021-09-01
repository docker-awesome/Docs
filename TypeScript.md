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

- `Partial<Type>`: 构造一个`把 Type 的所有属性设置为可选`的类型。此实用程序将返回表示给定类型的所有子集的类型。
  
  ```typescript
  interface Todo {
    title: string;
    description: string;
  }
  
  type OptionalTodo = Partial<Todo> // { title?: string; description?: string; }
  ```

- `Required<Type>`: 构造一个`把 Type 的所有属性设置为必选`的类型。与 Partial 相反。
  
  ```typescript
  interface Todo {
    title?: string;
    description?: string;
  }
  
  type RequiredTodo = Required<Todo> // { title: string; description: string; }
  ```
  
- `Pick<Type, Keys>`: 通过从 Type 中选取一组属性键（字符串文字或字符串文字的并集）来构造一个类型。
  
  ```typescript
  interface Todo {
    title: string;
    date: string;
    description: string;
  }
  
  type PickTodo = Pick<Todo, 'title' | 'description'> // { title: string; description: string; }
  ```

- `Omit<Type, Keys>`: 通过从 Type 中选取所有属性然后删除键（字符串文字或字符串文字的并集）来构造一个类型。
  
  ```typescript
  interface Todo {
    title: string;
    date: string;
    description: string;
  }
  
  type PickTodo = Omit<Todo, 'date'> // { title: string; description: string; }
  ```

- `Record<Keys,Type>`: 构造一个对象类型，其属性键为 Keys，属性值为 Type。此实用程序可用于将一种类型的属性映射到另一种类型。
  
  ```typescript
  interface Todo {
    title: string;
    date: string;
    description: string;
  }

  type Things = 'wash' | 'homework'
  
  /**
  {
    wash: { title: string; description: string; },
    homework: { title: string; description: string; },
  }
  */
  type PickTodo = Record<Things, Todo>
  ```

- `Exclude<Type, ExcludedUnion>`: 通过从 Type 中排除所有可分配给 ExcludedUnion 的联合成员来构造一个类型。
  
  ```typescript
  type T = Exclude<"a" | "b" | "c", "a">; // type T = "b" | "c";
  type T = Exclude<string | number | (() => void), Function>; // type T = string | number
  ```

- `Extract<Type, Union>`: 通过从 Type 中提取可分配给 Union 的所有联合成员来构造一个类型。
  
  ```typescript
  type T = Extract<"a" | "b" | "c", "a" | "e">; // type T = "a";
  type T = Extract<string | number | (() => void), Function>; // type T = () => void
  ```

- `Extract<Type, Union>`: 通过从 Type 中提取可分配给 Union 的所有联合成员来构造一个类型。

  ```typescript
  type T = Extract<"a" | "b" | "c", "a" | "e">; // type T = "a";
  type T = Extract<string | number | (() => void), Function>; // type T = () => void
  ```
