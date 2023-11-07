# Form-React-native
create a login form
import React from 'react';
import {Text, TextInput, View,  StyleSheet, Button} from 'react-native';
import { useState } from 'react'; 



const App = () => { 
const [name,setName]=useState("");
const [email, setEmail]=useState("");
const [password, setPassword]=useState(""); 
const[display,setDisplay]=useState(false);

const resetFormData=()=>{
  setDisplay(false);
  setName("");
  setEmail("");
  setPassword("");
}
  return (
    <View>                                          
      <Text style={{fontSize:30}}>Simple Form in React Native</Text>
       <Text style={{fontSize:30}}>Your name is :{name}</Text>
     <TextInput
     style={styles.textInput }
     placeholder='Enter your Name'
     value={name}
     onChangeText={(text)=>setName(text)}
     />
     <TextInput 
     style={styles.textInput}
     placeholder=' Enter User Email'
     value={email}
     onChangeText={(text)=>setEmail(text)}
     />
     <TextInput 
     style={styles.textInput}
     placeholder='Enter User Password'
     secureTextEntry={true}
     value={password}
     onChangeText={(text)=>setPassword(text)}
     />
     <View style={{marginBottom:10}}>
     <Button color={"green"} title='Print Details' onPress={()=>setDisplay(true)}/>
     </View>
     <Button title='Clear Details' onPress={()=>resetFormData(false)}/>
     <View>
      {
      display?
      <View>
        <Text style={{fontSize:35}}>User Name is :{name}</Text>
        <Text style={{fontSize:35}}>User Password is :{password}</Text>
        <Text style={{fontSize:35}}>User Email is :{email}</Text>
     </View>: null
     }
     </View>
      </View>
  );
};

const styles=StyleSheet.create({
  textInput:{fontSize:18,
    color:'blue',
    borderWidth:2,
    borderColor:'blue',
    margin:10
   }
})
export default App;
