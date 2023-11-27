
Steps:
1) get any data from twitter containing disney parks references 
    (this can be used later to expand project to other departments of the parks)
    
    for (int i=0; i<characterKEYWORDS.length(); i++):
        curKeyword = characterKEYWORDS[i];
        tweets with SELECT * FROM BIGQUERYFILE containing curKeyword

    # to see how large before proceeding
    SELECT COUNT(*) AS num_rows FROM yourTable

2) filter to just character meet& greets
