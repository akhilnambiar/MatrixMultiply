#pragma omp for schedule(dynamic)
    for (int j=0; j<m; j++)
	for (int i=n; i<n+n_pad; i++)
	    memset(A_T+i+j*(n+n_pad),0,sizeof(float));//This will add zeros to the columns
  #pragma omp for schedule(dynamic)
    for (int j=m;j<m+m_pad;j++)
        memset(A_T+j*(n+n_pad),0,sizeof(float)*(n+n_pad);//This will add new 0 rows
  }   
  float* C_new = malloc(ARRAY_SIZE*sizeof(float));
  #pragma omp for schedule(dynamic)
    for (int j=0;j<m_new)
	memset(C_new+j*n_new,0,sizeof(float)*n_new);
//The goal of this transposing is to make m divisible by 4, so we can use vectors, and columns divisible by 16, so we can use all 16 threads