### MainLayout

```
import React from 'react';
import PropTypes from 'prop-types';

const MainLayout = ({ children }) => {
  return (
    <section>
      <main>{children}</main>
    </section>
  );
};

MainLayout.propTypes = {
  children: PropTypes.node,
};

export default MainLayout;

```

{children} - this will pass all component data

### layout

```
import React from 'react';
import PropTypes from 'prop-types';

import '../../../styles/global.scss';

const Layout = ({ title, description, className, children }) => {
  return (
    <div>
      <div className='jumbotron'>
        <h2>{title}</h2>
        <p className='lead'>{description}</p>
      </div>

      <main className={className}>{children}</main>
    </div>
  );
};

Layout.propTypes = {
  children: PropTypes.node,
  title: PropTypes.string,
  description: PropTypes.string,
  className: PropTypes.any,
};


```
