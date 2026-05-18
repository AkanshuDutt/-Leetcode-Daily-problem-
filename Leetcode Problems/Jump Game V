var minJumps = function(arr) 
{
    let n = arr.length;

    let mp = new Map();

    for(let i = 0; i < n; i++)
    {
        if(!mp.has(arr[i]))
            mp.set(arr[i], []);

        mp.get(arr[i]).push(i);
    }

    let q = [];
    let visited = new Array(n).fill(false);

    q.push(0);
    visited[0] = true;

    let steps = 0;

    while(q.length)
    {
        let size = q.length;

        while(size--)
        {
            let currIdx = q.shift();

            if(currIdx === n - 1)
                return steps;

            //================================================================
            //EXPLORE ALL POSSIBLE OPTIONS

            if(currIdx + 1 < n && !visited[currIdx + 1]) //OPTION-1 (Move Forward)
            {
                visited[currIdx + 1] = true;
                q.push(currIdx + 1);
            }

            if(currIdx - 1 >= 0 && !visited[currIdx - 1]) //OPTION-2 (Move Backward)
            {
                visited[currIdx - 1] = true;
                q.push(currIdx - 1);
            }

            for(let newIdx of mp.get(arr[currIdx])) //OPTION-3 (Move to same valued idx)
            {                                       //newIdx could be before currIdx or after currIdx
                if(!visited[newIdx])
                {
                    visited[newIdx] = true;
                    q.push(newIdx);
                }
            }

            //===================================================================
            mp.set(arr[currIdx], []); //EXPLAINED BELOW :)
        }

        steps++;
    }

    return -1;
};
