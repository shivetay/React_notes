```
import {useState} from 'react

const Search = () => {
  const [search, setSearch] = useState('')

  return (
    <div>
    <input type='text' placeholder='Search here' onChange={e => {setSearch(e.target.value)}}/>
{myDataJSON.filter((val) => {
  if(search == ""){
    return val
  } else if (val.data.toLowerCase().includes(search.toLowerCase())){
    retunr val
  }
}).map((val) =>{
  return(
    <div>
    <p>{val.value}</p>
    </div>
  )
})

}

    </div>
  )
}


```
