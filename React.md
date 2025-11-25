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
```
import React from 'react';

class App extends React.Component {
  constructor(props) {
    super(props);
    // stateを定義してください
    this.state = {count:0}
  }
  
  render() {
    return (
      <div>
        <h1>
          {/* stateの値を表示してください */}
          {this.state.count}
          
        </h1>
        {/* <button>タグを追加してください */}
        <button>+</button>
        
      </div>
    );
  }
}

export default App;
```
```
import React from 'react';

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {count: 0};
  }
  
  // handleClickメソッドを定義してください
  handleClick(){
    this.setState({count: this.state.count + 1});
  }
  
  render() {
    return (
      <div>
        <h1>
          {this.state.count}
        </h1>
        {/* <button>タグ内でonClickイベントを追加してください */}
        <button onClick={()=>{this.handleClick()}}>+</button>
        
      </div>
    );
  }
}

export default App;
```
```
<!DOCTYPE html>
<html>
  <head>
    <title>React App</title>
  </head>
  <body>
    <!-- idを指定してください -->
    <div id="root"></div>
    
    <script src="bundle.js"></script>
  </body>
</html>
```
```
import React from 'react';

class App extends React.Component {
  render() {
    return (
      <div>
        {/* h1タグにクラス名を追加してください */}
        <h1 className='title'>Hello World</h1>
        
        <p>一緒にReactを学びましょう！</p>
      </div>
    );
  }
}

export default App;
```
```
// Reactをインポートしてください
import React from 'react';

// Languageクラスを定義してください
class Language extends React.Component{
  render() {
	    return (
  <div className='language-item'>
        <div className='language-name'>HTML & CSS</div>
        <img className='language-image' src='https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/react/html.svg' />
      </div>
      );
}
}
```
```
import React from 'react';
// Languageコンポーネントをインポートしてください
import Language from './Language'

class App extends React.Component {
  render() {
    return (
      <div>
        <h1>言語一覧</h1>
        <div className="language">
          {/* Languageコンポーネントを呼び出してください */}
          <Language />
          
        </div>
      </div>
    );
  }
}

export default App;

```
```
import React from 'react';
import Language from './Language';

class App extends React.Component {
  render() {
    return (
      <div>
        <h1>言語一覧</h1>
        <div className="language">
          <Language />
          {/* Languageコンポーネントを2回呼び出してください */}
          <Language />
          <Language />
        </div>
      </div>
    );
  }
}

export default App;
```
```
import React from 'react';
import Language from './Language';

class App extends React.Component {
  render() {
    return (
      <div>
        <h1>言語一覧</h1>
        <div className='language'>
          {/* HTML & CSSのpropsを渡してください */}
          <Language 
            name='HTML & CSS'
            image='https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/react/html.svg'
            
          />
          {/* JavaScriptのpropsを渡してください */}
          <Language 
            name='JavaScript'
            image='https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/react/es6.svg'
          />
          {/* Reactのpropsを渡してください */}
          <Language 
            name='React'
            image='https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/react/react.svg'
          />
        </div>
      </div>
    );
  }
}

export default App;
```
```
import React from 'react';

class Language extends React.Component {
  render() {
    return (
      <div className='language-item'>
        {/* props名nameの値を表示するように書き換えてください */}
        <div className='language-name'>
        {this.props.name}
        </div>
        
        {/* src属性の値を、props名imageの値に書き換えてください */}
        <img 
          className='language-image'
          src={this.props.image}
        />
        
      </div>
    );
  }
}

export default Language;
```
```
import React from 'react';
import Language from './Language';

class App extends React.Component {
  render() {
    // 指定されたコードを貼り付けてください
    const languageList = [
      {
        name: 'HTML & CSS',
        image: 'https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/react/html.svg'
      },
      {
        name: 'JavaScript',
        image: 'https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/react/es6.svg'
      },
      {
        name: 'React',
        image: 'https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/react/react.svg'
      },
      {
        name: 'Ruby',
        image: 'https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/react/ruby.svg'
      },
      {
        name: 'Ruby on Rails',
        image: 'https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/react/rails.svg'
      },
      {
        name: 'Python',
        image: 'https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/react/python.svg'
      }
    ];

    return (
      <div>
        <h1>言語一覧</h1>
        <div className='language'>

          {/* mapメソッドを用いて、Languageコンポーネントを表示してください */}
          {languageList.map((languageItem) => {
            return (
              // Languageコンポーネントを呼び出し、その中でpropsを渡してください
              name={languageItem.name}
              image={languageItem.image}
            )
          })}
          
        </div>
      </div>
    );
  }
}

export default App;
```
```
// Reactをインポートしてください
import React from 'react';

// Lessonクラスを定義してください
class Lesson extends React.Component{

// Lessonクラスをexportしてください
render(){
  return(
    <div className='lesson-card'>
        <div className='lesson-item'>
          <p></p>
          <img />
        </div>
      </div>
    );
}
}
export default Lesson;
```
