#### 组合设计模式（`Composite`）

【学习难度：★★★☆☆，使用频率：★★★★☆】

> <font color=#FF6800>将对象组成树形结构以表示“部分-整体”的层次结构。该模式可以使用户对单个和组合对象的使用具有一致性。</font>
>
> 使用场景，以下情况都成立时使用Composite模式：
>
> - 需要表示部分-整体的层次结构
> - 希望用户忽略组合对象与单个对象的不同，统一地使用组合结构中的所有对象。
>

1. 上ULM图：
![alt ](assets/组合设计模式.png)


2. 上代码：
下面的实现方式称为透明式，如果要实现安全式的组合模式只需要把其他管理子对象的方法声明在复合组合的对象中即可

```c#
using System;
using System.Collections.Generic;

namespace DesignerPattern
{
    public class CompositePattern
    {
        public static void TestCompositePattern()
        {
            Component cp1 = new Leaf();
            Component cp2 = new Composite();

            cp2.Add(cp1);

            cp1.Operation();
            cp2.Operation();
        }
    }

    public abstract class Component
    {
        protected List<Component> _components = new List<Component>();
        public abstract void Operation();
        public virtual void Add(Component component)
        {
            _components.Add(component);
        }
        public virtual void Remove(Component component)
        {
            _components.Remove(component);
        }
        public virtual IList<Component> GetChildren()
        {
            return _components;
        }
    }

    public class Leaf : Component
    {
        public override void Operation()
        {
            Console.WriteLine("Leaf Operate");
        }

        public override void Add(Component component)
        {
            throw new InvalidOperationException();
        }

        public override void Remove(Component component)
        {
            throw new InvalidOperationException();
        }

        public override IList<Component> GetChildren()
        {
            throw new InvalidOperationException();
        }
    }

    public class Composite : Component
    {
        public override void Operation()
        {
            foreach(var item in _components)
            {
                item.Operation();
            }
        }
    }
}

```

