// with deplicate but not count
public int count(int[] array, int target) {
  int i = 0;
  int j = array.length - 1;
  int count = 0;
  while (i < j) {
    int sum = array[i] + array[j];
    if (sum == target) {
      count++;
      while (i ＋ 1 < j && array[i + 1] == array[i]) {
        i++;
      }
      i++;
    } else if (sum > target) {
      i++;
    } else {
      j--;
    }
  }
  return count;
}

//with deplicate but count;
public int count(int[] array, int target) {
  int i = 0;
  int j = array.length - 1;
  int count = 0;
  while (i < j) {
    int sum = array[i] + array[j];
    if (array[i] == array[j]) {
      count += (j - i + 1) * (j - i) / 2; 
      break;
    }
    if (sum == target) {
      int count1 = 1;
      while (i + 1 < j && array[i] == array[i + 1]) {
        i++;
        count1++;
      }
      int count2 = 1;
      while (j - 1 > i && array[j - 1] == array[j]) {
        j--;
        count2++;
      }
      count += count1 * count2;
      i++;
      j--;
    } else if (sum > target) {
      j--;
    } else {
      i++;
    }
  }
  return count;
}
