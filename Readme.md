## Challenge From dotnetfiddle

```c#

using System.Collections.Generic;
using System;

public class Program
{
	public static void Main()
	{
		var inputList = new List<int>() { 1, 4, 5, 6, 7, 8 };
		var result = FindTwoSum(inputList, 12);

		Console.WriteLine("List of Indexes");
		result.ForEach(tuple => System.Console.WriteLine(tuple.Item1 + " and " + tuple.Item2));
	}
	/*
	Write a function that, given a list and a target sum, returns zero-based indexes of all two distinct elements whose sum is equal to the target sum. 
	*/
	public static List<Tuple<int, int>> FindTwoSum(List<int> list, int sum)
	{
		int firtIndex = 0;
		int secondIndex = 0;
		int total = 0;
		List<Tuple<int, int>> listOfIndex = new List<Tuple<int, int>>();

		for (int i = firtIndex; i < list.Count; i++)
		{
			secondIndex += 1;
			for (int z = secondIndex; z < list.Count; z++)
			{
				total = list[i] + list[z];
				if (total == sum)
				{
					var tuple = Tuple.Create<int, int>(i, z);
					listOfIndex.Add(tuple);
				}
			}
		}
		if (listOfIndex.Count == 0)
			return null;

		return listOfIndex;
	}


}
```
