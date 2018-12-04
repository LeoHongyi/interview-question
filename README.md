# interview-question
getbatch

const getValueList = (inputJSON, from, to, curLevel, res) => {
	res = !res ? [] : res;
	curLevel = !curLevel ? 0 : curLevel;
	for (let i = 0; i < inputJSON.length; i++) {
		const curEle = inputJSON[i];
		// if children length of curEle is larger then 0, it should go deeper;
		if (curEle.children.length > 0) {
			getValueList(curEle, from, to, curLevel + 1, res);	
} else {
	if (curLevel >= from && curLevel <= to) res.push(curEle);
}
}
return res;
}
