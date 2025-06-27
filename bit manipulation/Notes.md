code decimaltobinary
void decimalToBinary(int n) {
    if (n == 0) return;
    decimalToBinary(n / 2);
    cout << (n % 2);
}
time complexity=O(log n) in each recursive call we are dividing n by 2 so number of rec calls= log n(base 2)
space complexity=O(log n) as log n recursivecalls are stacked
