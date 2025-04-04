import { useState } from 'react';
import { Text, View, SafeAreaView,StyleSheet, TextInput, TouchableOpacity, Button } from 'react-native';


// Importante importar as funções que você irá utilizar
// flex para padronizar tamanhos
function App() {
  const [name, setName] = useState('Dandan');
  const [sobrenome, setSobrenome] = useState('Lima');
  const [age, setAge] = useState(25);
  const [input, setInput] = useState('');

  function getName(text){
    setName(text);
  }
  function Saveinfo(){
    setName(input);
  }
  return (
    <View>
      <Text style={{fontSize:40,marginTop:20}}>Nome</Text>
      <TextInput style={styles.input} onChangeText={(text)=>setInput(text)} placeholder='Digita seu nome:'/>
      <Text style={{fontSize:40}}>{name}</Text>
      <Button title='Salvar' onPress={setInput}></Button>
      <TextInput style={styles.input} placeholder='Digita seu sobrenome:' onChangeText={(text)=>getName(text)}/>
      <Text style={{fontSize:40}}>{sobrenome}</Text>
      <TextInput style={styles.input} onChangeText={setAge} placeholder='Digita sua idade:'/>
      <Text style={{fontSize:40}}>{name} {sobrenome} {age}</Text>
    </View>
  );
}

export default App;


// esse styles e o nome da variavel
let styles = StyleSheet.create({
  input:{
    borderWidth:10,
    marginTop: 12,
    padding: 12,
    borderRadius:25,
    borderColor: '#ccc',
    color:'red',
    fontWeight:'bold',
    fontSize:24
  }
})
