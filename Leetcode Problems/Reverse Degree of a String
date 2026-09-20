var reverseDegree = function(s) {
    let sum = 0;
    for (let i = 0; i < s.length; i++) {
        const reverseValue = 26 - (s.charCodeAt(i) - 97);
        const position = i + 1;

        sum += reverseValue * position;
    }
    return sum;
};
