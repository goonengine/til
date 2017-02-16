# Usage of Reflection
It's useful for getting values of an instance.

``` C#
public class Hero {
	public string nick { get; set; }
	public string name { get; set; }

	private int age;
	private string gender;
	private bool is_fly;

	public Hero ( string nick, string name, bool b_fly )
	{
		this.age = age;
		this.gender = gender;
		this.is_fly = b_fly;
	}

	public void flying()
	{
		if ( is_fly )
			Console.WriteLine("I can fly!");
		else
			Console.WriteLine("I can't fly, but I have some great force!");
	}
}

public class Program
{
	public static void Main ( string[] args )
	{
		Hero hero = new Hero("-1", "Man?", true);
		hero.nick = "The Man of Steel";
		hero.name = "Superman";
		Type r_type = hero.GetType();

		ConstructorInfo[] constructor_info = r_type.GetConstructors();
		foreach ( ConstructorInfo val in constructor_info )
		{
			Console.WriteLine("Constructor: {0}", val);
		}

		MemberInfo[] member_info = r_type.GetMethods();
		foreach ( MemberInfo val in member_info )
		{
			Console.WriteLine("Member: {0}", val);
		}

		FieldInfo[] field_info = r_type.GetFields();
		foreach ( FieldInfo val in field_info )
		{
			Console.WriteLine("Field: {0}", val);
		}

		PropertyInfo[] property_info = r_type.GetProperties();
		foreach ( PropertyInfo val in property_info )
		{
			Console.WriteLine("Property: {0}={1}", val.Name, val.GetValue(hero));
		}
	}
}
```