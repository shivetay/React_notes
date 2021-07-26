```
import React, { Fragment, useEffect } from 'react';
import { useDispatch, useSelector } from 'react-redux';

import { listProducts } from '../../../redux/productReducers';
import Product from './Product';

const Products = () => {
  const dispatch = useDispatch(); - dispatch actions from redux
  const productList = useSelector((state) => state.productList);
  const { loading, error, products } = productList;

  useEffect(() => {
    dispatch(listProducts());
  }, [dispatch]);

  return (
    <Fragment>
      {loading ? (
        <h1>Products Loading...</h1>
      ) : error ? (
        <h3>{error}</h3>
      ) : (
        <Fragment>
          {products.map((product) => (
            <Product key={product._id} productData={product} />
          ))}
        </Fragment>
      )}
    </Fragment>
  );
};

export default Products;
```

```
import React, { useState } from 'react';
import { useDispatch } from 'react-redux';
import { searchRepo } from '../redux/ActionCreator';

const RepoList: React.FC = () => {
  const [term, setTerm] = useState(''); - set state for function component
  const dispatch = useDispatch();

  const onSubmit = (e: React.FormEvent<HTMLFormElement>) => {
    e.preventDefault();
    dispatch(searchRepo(term));
  };
  return (
    <div>
      <form onSubmit={onSubmit}>
        <input value={term} onChange={(e) => setTerm(e.target.value)} />
        <button>Search</button>
      </form>
    </div>
  );
};

export default RepoList;
```
