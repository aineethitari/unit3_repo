# Quiz 33
## Code

def list_pairing(list1:list,list2:list)->list:
    output = []
    for i in range(len(list1)):
        for n in range(len(list2)):
            if list1[i] == list2[n]:
               output.append(list1[i])

    return output


## Test Result

<img width="1061" alt="quiz033 test" src="https://user-images.githubusercontent.com/112055062/211439705-e5cd31df-b4f4-46cc-be74-167119ab87d0.png">
