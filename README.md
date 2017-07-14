## Strategy Pattern

### Introduction
Strategy pattern can be categorized as behavioral design pattern and it is simple and powerful. It can be considered in a kind of scenario where your object would perform a common action and that too selecting from various options available.

### UML class diagram
![Image](http://www.dofactory.com/images/diagrams/net/strategy.gif)

### How it works?
Let’s understand the widely accepted definition of strategy pattern which you can find from various resources on net. “**Strategy pattern defines a family of algorithms, encapsulates each one of them and makes them interchangeable.**” Confused with the definition? let’s try to break it in three parts:-

1) **Family of Algorithms-** The definition says that the pattern defines the family of algorithms- it means we have functionality (in these algorithms) which will do the same common thing for our object, but in different ways.

2) **Encapsulate each one of them-** The pattern would force you to place your algorithms in different classes (encapsulate them). Doing so would help us in selecting the appropriate algorithm for our object.

3) **Make them interchangeable-** The beauty with strategy pattern is we can select at run time which algorithm we should apply to our object and can replace them with one another

### Using the code

Let’s go through an example which would use the strategy pattern and would make everything clear.

```markdown

    public interface IFormat
    {
        bool IsApplicable(int indicador);
        void Proceed();
    }
```

```markdown    
    public abstract class BaseFormat : IFormat
    {
        protected int commonVariable = 0;
        public abstract bool IsApplicable(int indicador);

        public void Proceed()
        {
            commonVariable = 1;
            Console.Write("Something Common");
            ExecuteProceed();
            ExecuteProceed1();
        }

        public abstract void ExecuteProceed();
        public virtual void ExecuteProceed1()
        {
            Console.Write("just format 1");
        }
    }

```
```markdown   
    public class Format1 : BaseFormat
    {
        public override void ExecuteProceed()
        {
            commonVariable = commonVariable + 5;
            Console.WriteLine("Format 1");
        }

        public override bool IsApplicable(int indicador)
        {
            if (indicador == 1) return true;
            return false;

        }

    }
```

```markdown

     public class Format2 : BaseFormat
    {
        public override void ExecuteProceed()
        {
            Console.WriteLine("Format 2");
        }

        public override bool IsApplicable(int indicador)
        {
            if (indicador == 2) return true;
            return false;
        }

        public override void ExecuteProceed1()
        {
            Console.WriteLine("just format 22 with virtual");
        }

    }
    
```

```markdown    

     class Program
    {
        static void Main(string[] args)
        {
            Random rnd = new Random();
            int indicador = 1;
            var formatList = GetFormats();
            var format = formatList.FirstOrDefault(x => x.IsApplicable(indicador));
            format.Proceed();
            Console.ReadLine();
        }

        private static List<IFormat> GetFormats()
        {
            var formatList = new List<IFormat>()
            {
                new Format1(),
                new Format2()
            };
            return formatList;

        }
    }
            
```

For more details see [The Strategy Pattern Repository](https://github.com/smithasencios/StrategyPattern).

