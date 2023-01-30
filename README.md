# react-native-iconfont-mapper

Simple script to transform iconfont file(.ttf) to a js mapping moudle . The js mapping moudle used in react native iconfont.

# Requirement

Require python package `fonttools`.

> pip install fonttools

If on Mac OS El Capitan and later got the error:

```
Could not install packages due to an EnvironmentError: [Errno 1] Operation not permitted: '/System/Library/Frameworks/Python.framework/Versions/2.7/share'
```

try to use:

> pip install fonttools --user

# Usage

`$ python iconfont-mapper.py fontawesome.ttf fontawesomeConf.js `

It will read the `fontawesome.ttf` file and generate fontawesomeConf.js .

The fontawesomeConf.js like below

```javascript
var map = {"arrow":62976,"checked":62977,"checked-s":62978,"tag-svip":62995};
;module.exports = (name)=>String.fromCharCode(map[name]); 
;module.exports.map = map;
```

and use in react native:

```javascript
import icon from "./fontConf";
export default class  IconExample extends Component {
    render() {
        return (
            <View style={styles.container}>
                <Text style={{fontFamily: 'FontIconQui',fontSize:30}}>
                    arrow-icon:{icon('arrow')}
                </Text>
                <Text style={{fontFamily: 'FontIconQui',fontSize:30, color:"#ff4444"}}>
                    checked:{icon('checked')}
                </Text>
                <Text style={{fontFamily: 'FontIconQui',fontSize:30, color:"#ff4444"}}>
                    tag-svip:{icon('tag-svip')}
                </Text>
            </View>
        )
    }
}
```

# License
MIT
