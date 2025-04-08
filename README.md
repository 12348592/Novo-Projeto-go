# Novo-Projeto-go
package main

import (
	"fmt"
	"github.com/seu-usuario/meu-projeto-go/internal/analytics"
	"github.com/seu-usuario/meu-projeto-go/internal/data"
)

func main() {
	// Carrega dados
	dataset := data.LoadSalesData()

	// Inicializa analisador
	analyzer := analytics.NewAnalyzer(dataset)

	// Resultados
	fmt.Println("=== Análise Básica ===")
	fmt.Printf("Média: %.2f\n", analyzer.Media())
	fmt.Printf("Máximo: %.2f\n", analyzer.Maximo())
	fmt.Printf("Mínimo: %.2f\n", analyzer.Minimo())

	// Filtros
	fmt.Println("\n=== Análise Avançada ===")
	fmt.Println("Valores acima da média:", analyzer.Filtrar(analytics.AcimaDaMedia))
}
