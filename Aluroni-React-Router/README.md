# Desafio - crie uma rota de redirecionamento do usuário aplicando a função abaixo 

import { BrowserRouter as Router, Routes, Route, useParams, Navigate } from "react-router-dom"

function Admin() {
 const params = useParams()
 if (params.user !== "banana") {
   return <Navigate to="/" />
 }
 return (
   <>
     <h1>Área restrita!</h1>
   </>
 )
}
function PaginaInicial() {
 return (
   <h1>Página Inicial</h1>
 )
}
function AppRouter() {
 return (
   <Router>
     <Routes>
       <Route path="/" element={<PaginaInicial />} />
       <Route path="/admin/:user" element={<Admin />} />
     </Routes>
   </Router>
 )
}
export default AppRouter
