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
```
import React from 'react';

class Lesson extends React.Component {
  render() {
    return (
      <div className='lesson-card'>
        <div className='lesson-item'>
          {/* props名nameの値を入れてください*/}
          <p>{this.props.name}</p>
          
          {/* src属性に、props名imageの値を指定してください */}
          <img src={this.props.image} />
          
        </div>
      </div>
    );
  }
}

export default Lesson;
```
```
import React from 'react';

class Lesson extends React.Component {
  render() {
    return (
      <div className='lesson-card'>
        <div className='lesson-item'>
          <p>{this.props.name}</p>
          <img src={this.props.image} />
        </div>
        {/* モーダルを用意してください */}
        <div className='modal'>
          <div className='modal-inner'>
            <div className='modal-header'></div>
            <div className='modal-introduction'>
              {/* レッスンの名前を表示してください */}
              <h2>{this.props.name}</h2>
              
              {/* レッスンの紹介文を表示してください */}
              <p>{this.props.introduction}</p>
              
            </div>
            <button className='modal-close-btn'>
              とじる
            </button>
          </div>
        </div>
        
      </div>
    );
  }
}

export default Lesson;
```
```
import React from 'react';

class Lesson extends React.Component {
  // constructorを定義してください
  constructor(props) {
    super(props);
    // stateの初期値を定義してください
    this.state={isModalOpen:false}
    
  };
  
  render() {
    return (
      <div className='lesson-card'>
        <div className='lesson-item'>
          <p>{this.props.name}</p>
          <img src={this.props.image} />
        </div>
        <div className='modal'>
          <div className='modal-inner'>
            <div className='modal-header'></div>
            <div className='modal-introduction'>
              <h2>{this.props.name}</h2>
              <p>{this.props.introduction}</p>
            </div>
            <button className='modal-close-btn'>
              とじる
            </button>
          </div>
        </div>
      </div>
      
    );
  }
}

export default Lesson;
```
```
import React from 'react';

class Lesson extends React.Component {
  constructor(props) {
    super(props);
    this.state = {isModalOpen: false};
  }

  render() {
    // 変数modalを定義してください
   let modal;
    
    // if文を用意してください
    if (this.state.isModalOpen){
      modal=(<div className='modal'>
          <div className='modal-inner'>
            <div className='modal-header'></div>
            <div className='modal-introduction'>
              <h2>{this.props.name}</h2>
              <p>{this.props.introduction}</p>
            </div>
            <button className='modal-close-btn'>
              とじる
            </button>
          </div>
        </div>);
    }
    
    return (
      <div className='lesson-card'>
        <div className='lesson-item'>
          <p>{this.props.name}</p>
          <img src={this.props.image} />
        </div>
{modal}
        
        {/* 変数モーダルを表示してください */}
      </div>
    );
  }
}

export default Lesson;
```
```
import React from 'react';

class Lesson extends React.Component {
  constructor(props) {
    super(props);
    this.state = {isModalOpen: false};
  }
  
  // handleClickLessonメソッドを定義してください
  handleClickLesson(){
  this.setState({isModalOpen:ture});
  
  render() {
    let modal;
    if (this.state.isModalOpen) {
      modal = (
        <div className='modal'>
          <div className='modal-inner'>
            <div className='modal-header'></div>
            <div className='modal-introduction'>
              <h2>{this.props.name}</h2>
              <p>{this.props.introduction}</p>
            </div>
            <button className='modal-close-btn'>
              とじる
            </button>
          </div>
        </div>
      );
    }
    return (
      <div className='lesson-card'>
        {/* onClickイベントを追加してください */}
        <div
          className='lesson-item'
          onClick={()=>{this.handleClickLesson()}}
        >
          <p>{this.props.name}</p>
          <img src={this.props.image} />
        </div>
        {modal}
      </div>
    );
  }
}

export default Lesson;
```
```
import React from 'react';

class Lesson extends React.Component {
  constructor(props) {
    super(props);
    this.state = {isModalOpen: false};
  }

  handleClickLesson() {
    this.setState({isModalOpen: true});
  }
  
  // handleClickCloseメソッドを定義してください
  handleClickClose(){
    this.setState({isModalOpen: false});
  }

  render() {
    let modal;
    if (this.state.isModalOpen) {
      modal = (
        <div className='modal'>
          <div className='modal-inner'>
            <div className='modal-header'></div>
            <div className='modal-introduction'>
              <h2>{this.props.name}</h2>
              <p>{this.props.introduction}</p>
            </div>
            {/* onClickイベントを追加してください */}
            <button
              className='modal-close-btn'
          　onClick={() => {this.handleClickClose()}}
            >
              とじる
            </button>
          </div>
        </div>
      );
    }

    return (
      <div className='lesson-card'>
        <div
          className='lesson-item'
          onClick={() => {this.handleClickLesson()}}
        >
          <p>{this.props.name}</p>
          <img src={this.props.image} />
        </div>
        {modal}
      </div>
    );
  }
}

export default Lesson;
```
```
import React from 'react';

class ContactForm extends React.Component {
  render() {
    return (
      <div className='contact-form'>
        <form>
          <p>メールアドレス（必須）</p>
          {/* inputタグを追加してください */}
          <input />
          
          <p>お問い合わせ内容（必須）</p>
          {/* textareaタグを追加してください */}
          <textarea />
          
          {/* 送信ボタンを追加してください */}
          <input
          type='submit'
          value='送信'
        </form>
      </div>
    );
  }
}

export default ContactForm;
```
```
import React from 'react';

class ContactForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      /* isSubmittedというstateを定義してください */
      isSubmitted:false
    };
  }

  render() {
    /* 空の変数contactFormを定義してください */
    let contactForm;
    
    /* isSubmittedを条件式とするif文を作成してください */
    if (this.state.isSubmitted){
    contactForm=(
<div className='contact-submit-message'>
          送信完了
        </div>
      );
    } else {            
     contactForm = (
    
    <form>
          <p>メールアドレス（必須）</p>
          <input />
          <p>お問い合わせ内容（必須）</p>
          <textarea />
          <input
            type='submit'
            value='送信'
          />
        </form>
        );
    }
    return (
      <div className='contact-form'>
        {/* 以下を削除して、変数contactFormを表示してください */}
{contactForm}
      </div>
      
    );
  }
}

export default ContactForm;
```
```
import React from 'react';

class ContactForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      isSubmitted: false,
    };
  }

  /* handleSubmitメソッドを定義してください  */
  handleSubmit(){
    this.setState({isSubmitted:true});
  }

  render() {
    let contactForm;
    if (this.state.isSubmitted) {
      contactForm = (
        <div className='contact-submit-message'>
          送信完了
        </div>
      );
    } else {
      contactForm = (
        /* formタグにonSubmitを追加してください */
        <form onSubmit={()=>{this.handleSubmit} }>
          <p>メールアドレス（必須）</p>
          <input />
          <p>お問い合わせ内容（必須）</p>
          <textarea />
          <input
            type='submit'
            value='送信'
          />
        </form>
      );
    }
    
    return (
      <div className='contact-form'>
        {contactForm}
      </div>
    );
  }
}

export default ContactForm;
```
```
import React from 'react';

class ContactForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      isSubmitted: false,
      /* stateにemailを追加してください */
      email:'mail@prog-8.com'
    };
  }

  handleSubmit() {
    this.setState({isSubmitted: true});
  }

  render() {
    let contactForm;
    if (this.state.isSubmitted) {
      contactForm = (
        <div className='contact-submit-message'>
          送信完了
        </div>
      );
    } else {
      contactForm = (
        <form onSubmit={() => {this.handleSubmit()}}>
          <p>メールアドレス（必須）</p>
          {/* inputにvalue属性を加えてください */}
          <input  value={this.state.email}/>
          
          <p>お問い合わせ内容（必須）</p>
          <textarea />
          <input
            type='submit'
            value='送信'
          />
        </form>
      );
    }
    
    return (
      <div className='contact-form'>
        {contactForm}
      </div>
    );
  }
}

export default ContactForm;
```
```
import React from 'react';

class ContactForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      isSubmitted: false,
      email: '',
    };
  }

  handleSubmit() {
    this.setState({isSubmitted: true});
  }

  render() {
    let contactForm;
    if (this.state.isSubmitted) {
      contactForm = (
        <div className='contact-submit-message'>
          送信完了
        </div>
      );
    } else {
      contactForm = (
        <form onSubmit={() => {this.handleSubmit()}}>
          <p>メールアドレス（必須）</p>
          {/* inputにonChangeイベントを追記してください */}
          <input
            value={this.state.email}
            onChange={(event)=>{console.log(event.target.value)}}
          />
          <p>お問い合わせ内容（必須）</p>
          <textarea />
          <input
            type='submit'
            value='送信'
          />
        </form>
      );
    }
    
    return (
      <div className='contact-form'>
        {contactForm}
      </div>
    );
  }
}

export default ContactForm;
```
```
import React from 'react';

class ContactForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      isSubmitted: false,
      email: '',
    };
  }

  /* handleEmailChangeという名前のメソッドを定義してください */
  handleEmailChange(event){
    const inputValue=event.target.value;
    this.setState({email: inputValue});
  }

  handleSubmit() {
    this.setState({isSubmitted: true});
  }

  render() {
    let contactForm;
    if (this.state.isSubmitted) {
      contactForm = (
        <div className='contact-submit-message'>
          送信完了
        </div>
      );
    } else {
      contactForm = (
        <form onSubmit={() => {this.handleSubmit()}}>
          <p>メールアドレス（必須）</p>
          <input
            value={this.state.email}
            /* console.log(event.target.value) の部分を削除してください */
            /* handleEmailChangeを実行するようにしてください */
            onChange={(event) => {handleEmailChange(event)}}
          />
          <p>お問い合わせ内容（必須）</p>
          <textarea />
          <input
            type='submit'
            value='送信'
          />
        </form>
      );
    }
    
    return (
      <div className='contact-form'>
        {contactForm}
      </div>
    );
  }
}

export default ContactForm;
```
