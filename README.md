# ES6_App
ES6 語法糖省去很多綁定的麻煩


    import React, {Component} from 'react';

    class ES_Six extends React.Component{

        constructor(props){
            super(props)

            this.state = {
                a:0,
                b:{x: 0, y:0},
                c:"",
                d:[],
                e:{}
            };
            //如下免去 bind()
            //因為使用 ES6 語法糖
        }

        componentDidUpdate(){

            this.setState({
                a: 1,
                b:{x:11, y:12},
                c: 'haha',
                d: ["bread","tea","coffee","steamed food"],
                e:{}
            })

        }

        // 語法 ES 寫法
        // 自動 bind()
        funcCalled = () => {

            this.setState({a:12})

        }

        render(){

            const {g, gg} = this.state; // function component 才能用useState()

            return(
                <div>
                    <p>{this.state.b.x}</p>
                    <p> {this.funcCalled()}</p>
                    <button onClick={this.funcCalled}></button>
                </div>
            )
        }
    }
