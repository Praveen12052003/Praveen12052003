package main
import (
	"fmt"
	"math"
)
func findSecondLargest(arr []int) (int, error) {
	if len(arr) < 2 {
		return 0, fmt.Errorf("Array must have at least two elements")
	}
	largest := math.MinInt64
	secondLargest := math.MinInt64
	for _, num := range arr {
		if num > largest {
			secondLargest = largest
			largest = num
		} else if num > secondLargest && num != largest {
			secondLargest = num
		}
	}
	if secondLargest == math.MinInt64 {
		return 0, fmt.Errorf("There is no second largest element")
	}
	return secondLargest, nil
}
func main() {
	arr1 := []int{5, 7, 12, 3, 9, 11}
	secondLargest1, err1 := findSecondLargest(arr1)
	if err1 != nil {
		fmt.Println(err1)
	} else {
		fmt.Println("The second largest element in arr1 is:", secondLargest1)
	}
	arr2 := []int{1, 10, 5, 10, 9}
	secondLargest2, err2 := findSecondLargest(arr2)
	if err2 != nil {
		fmt.Println(err2)
	} else {
		fmt.Println("The second largest element in arr2 is:", secondLargest2)
	}
	arr3 := []int{3, 3, 3, 3, 3}
	secondLargest3, err3 := findSecondLargest(arr3)
	if err3 != nil {
		fmt.Println(err3)
	} else {
		fmt.Println("The second largest element in arr3 is:", secondLargest3)
	}
	arr4 := []int{1, 2}
	secondLargest4, err4 := findSecondLargest(arr4)
	if err4 != nil {
		fmt.Println(err4)
	} else {
		fmt.Println("The second largest element in arr4 is:", secondLargest4)
	}
}
