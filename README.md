# EX.-NO-1-C-IMPLEMENTATION-OF-HILL-CIPHER

## AIM:
To write a C program to implement the hill cipher substitution techniques.

## ALGORITHM:

STEP-1: Read the plain text and key from the user.

STEP-2: Split the plain text into groups of length three.

STEP-3: Arrange the keyword in a 3*3 matrix.

STEP-4: Multiply the two matrices to obtain the cipher text of length three.

STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM: 
```
keyMatrix = [[0] * 3 for i in range(3)]

messageVector = [[0] for i in range(3)]

cipherMatrix = [[0] for i in range(3)]

def getKeyMatrix(key):
	k = 0
	for i in range(3):
		for j in range(3):
			keyMatrix[i][j] = ord(key[k]) % 65
			k += 1

def encrypt(messageVector):
	for i in range(3):
		for j in range(1):
			cipherMatrix[i][j] = 0
			for x in range(3):
				cipherMatrix[i][j] += (keyMatrix[i][x] *
									messageVector[x][j])
			cipherMatrix[i][j] = cipherMatrix[i][j] % 26

def HillCipher(message, key):
	getKeyMatrix(key)

	for i in range(3):
		messageVector[i][0] = ord(message[i]) % 65

	encrypt(messageVector)
	CipherText = []
	for i in range(3):
		CipherText.append(chr(cipherMatrix[i][0] + 65))
	print("Ciphertext: ", "".join(CipherText))

def main():
	message = "ACT"
	key = "GYBNQKURP"
	print("Original Text: ",message)
	HillCipher(message, key)

if __name__ == "__main__":
	main()
```

## OUTPUT:
![Screenshot 2024-10-26 133130](https://github.com/user-attachments/assets/2f4b8b1c-44df-42df-b049-b640ea7b3fb0)

## RESULT:
  Thus the hill cipher substitution technique had been implemented successfully.
