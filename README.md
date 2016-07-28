# LevelUp.Serializer.JsonNet

Example
```C#
using System;
using LevelUp.Serializer;
using LevelUp.Serializer.JsonNet;

namespace ConsoleApplication46
{
    public class Person
    {
        public string Name { get; set; }
    }

    class Program
    {
        static void Main(string[] args)
        {
            var larry = new Person()
            {
                Name = "Larry Nung"
            };

            var serializer = new JsonNetSerializer();
            var json = serializer.SerializeToText(larry);

            Console.WriteLine(json);
            Serializer.RegisterSerializer(SerializerType.Json, typeof(JsonNetSerializer));
            json = Serializer.SerializeToText(larry, SerializerType.Json);

            Console.WriteLine(json);


            json = larry.ToJSON();

            Console.WriteLine(json);


            larry = Serializer.DeSerializeFromText<Person>(json, SerializerType.Json);

            Console.WriteLine(larry.Name);
        }
    }
}
```
