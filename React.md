```
import React from 'react';

class App extends React.Component {
  render() {
    return (
      <h1>Hello React</h1>
    );
  }
}

export default App;
```
```
HTMLではなく、JSX
```
```
import React from 'react';

class App extends React.Component {
  render() {
    return (
      <div>
        {/* <h1>タグを用いて、「Hello World」と表示してください */}
        <h1>Hello World</h1>
        
        {/* <p>タグを用いて、「一緒にReactを学びましょう！」と表示してください */}
        <p>一緒にReactを学びましょう！</p>
        
      </div>
    );
  }
}

export default App;
```
```
import React from 'react';

class App extends React.Component {
  render() {
    return (
      <div>
        <h1>Hello World</h1>
        <p>一緒にReactを学びましょう！</p>
        {/* <img>タグを用いて、画像を表示してください */}
        <img src='https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/react/ninjawanko.png'/>
        
      </div>
    );
  }
}

export default App;
```
```
// Reactをインポートしてください
import React from 'react';

// Appクラスを定義してください
class App extends React.Component{ 
render(){
return (
      <h1>Hello React</h1>
    );
}
// Appクラスをエクスポートしてください
}
export default App;
```
```
import React from 'react';

class App extends React.Component {
  render() {
    // 定数nameを定義してください
    const name ='にんじゃわんこ';
    
    // 定数imgUrlを定義してください
    const imgUrl ='https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/react/ninjawanko.png'
    
    return (
      <div>
        {/* 定数nameを用いてにんじゃわんこと表示されるようにしてください */}
        <h1>{name}</h1>
        
        {/* 定数imgUrlを用いて画像が表示されるようにしてください */}
        <img src={imgUrl}/>
        
      </div>
    );
  }
}

export default App;
```
```
import React from 'react';

class App extends React.Component {
  render() {
    return (
    	<div>
    	  <h1>こんにちは、にんじゃわんこさん！</h1>
        {/* buttonタグ内に、コンソールに名前を出力するonClickイベントを追加してください */}
        <button onClick={()=>{console.log('ひつじ仙人')}}>ひつじ仙人</button>
        
        {/* buttonタグ内に、コンソールに名前を出力するonClickイベントを追加してください */}
        <button onClick={()=>{console.log('にんじゃわんこ')}}>にんじゃわんこ</button>
        
      </div>
    );
  }
}

export default App;

```
```
import React from 'react';

class App extends React.Component {
  // constructorを貼り付けてください
  constructor(props) {
    super(props);
    // stateを定義してください
    this.state = {name:'にんじゃわんこ'};
    
  }
  
  render() {
    return (
    	<div>
    	  <h1>こんにちは、にんじゃわんこさん！</h1>
        <button onClick={() => {console.log('ひつじ仙人')}}>ひつじ仙人</button>
        <button onClick={() => {console.log('にんじゃわんこ')}}>にんじゃわんこ</button>
      </div>
    );
  }
}

export default App;
```
```
this.setState({プロパティ名: 変更する値})とすることで、指定されたプロパティに対応するstateの値が変更される
```
