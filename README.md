package main

import (
	"fmt"
	"strings"
)

type Profile struct {
	Name       string
	Roles      []string
	Working    string
	WorkingURL string
	Learning   string
	AskAbout   []string
	Email      string
	Languages  []string
}

const (
	reset  = "\033[0m"
	bold   = "\033[1m"
	cyan   = "\033[36m"
	green  = "\033[32m"
	yellow = "\033[33m"
)

func main() {
	p := Profile{
		Name:       "Rudin",
		Roles:      []string{"Fullstack Developer", "Cyber Security"},
		Working:    "RekberinAja",
		WorkingURL: "https://rekberinaja.com/",
		Learning:   "Modern Technologies",
		AskAbout:   []string{"Golang", "Rust", "Java"},
		Email:      "rudin@rekberinaja.com",
		Languages:  []string{"Go", "Rust", "Java"},
	}

	line := strings.Repeat("═", 50)

	fmt.Printf("%s%s%s\n", cyan, line, reset)
	fmt.Printf("%s👋 Hi, I'm %s%s\n", bold, p.Name, reset)
	fmt.Printf("%s%s%s\n", cyan, line, reset)

	fmt.Printf("%s💼 Role      :%s %s\n", yellow, reset, strings.Join(p.Roles, " & "))
	fmt.Printf("%s🔭 Building  :%s %s (%s)\n", yellow, reset, p.Working, p.WorkingURL)
	fmt.Printf("%s🌱 Learning  :%s %s\n", yellow, reset, p.Learning)
	fmt.Printf("%s💬 Ask me    :%s %s\n", yellow, reset, strings.Join(p.AskAbout, ", "))
	fmt.Printf("%s📫 Contact   :%s %s\n", yellow, reset, p.Email)

	fmt.Printf("\n%sLanguages & Tools:%s\n", green, reset)
	for _, l := range p.Languages {
		fmt.Printf("  %s• %s%s\n", green, l, reset)
	}

	fmt.Printf("%s%s%s\n", cyan, line, reset)
}
