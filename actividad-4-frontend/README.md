[Documentacion_Frontend.docx.docx](https://github.com/user-attachments/files/20432316/Documentacion_Frontend.docx.docx)
import React, { useState, useEffect } from 'react';
import axios from 'axios';

function App() {
  const [results, setResults] = useState([]);

  useEffect(() => {
    axios.get('https://api-ejemplo.com/results')
      .then(res => setResults(res.data));
  }, []);

  return (
    <div>
      <h1>Resultados Médicos</h1>
      <ul>
        {results.map(item => (
          <li key={item.id}>{item.nombreExamen}</li>
        ))}
      </ul>
    </div>
  );
}

export default App;
