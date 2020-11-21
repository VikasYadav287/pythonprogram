# pythonprogram
def smallestSubsequence(str):       
		dict={}
		for i in range(len(str)):
			dict[str[i]]=i
		stack=[]
		for i in range(len(str)):
			if str[i] in stack:
				continue
			while stack and stack[-1]>str[i] and dict[stack[-1]]>i:
					stack.pop()
			if str[i] not in stack:
				stack.append(str[i])
		return ''.join(stack)
s=input("Enter the string")
print(len(smallestSubsequence(s)))
