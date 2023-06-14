Classe ATOR E FILME-----------------------------------------------------------------------

public class Ator {
    private String nome;
    private int quantidadeEstrelas;
    
    // Construtor
    public Ator(String nome, int quantidadeEstrelas) {
        this.nome = nome;
        this.quantidadeEstrelas = quantidadeEstrelas;
    }
    
    // Getters e Setters
    public String getNome() {
        return nome;
    }
    
    public void setNome(String nome) {
        this.nome = nome;
    }
    
    public int getQuantidadeEstrelas() {
        return quantidadeEstrelas;
    }
    
    public void setQuantidadeEstrelas(int quantidadeEstrelas) {
        this.quantidadeEstrelas = quantidadeEstrelas;
    }
}

public class Filme {
    private String titulo;
    private String descricao;
    private int anoLancamento;
    private List<Ator> atores;
    
    // Construtor
    public Filme(String titulo, String descricao, int anoLancamento) {
        this.titulo = titulo;
        this.descricao = descricao;
        this.anoLancamento = anoLancamento;
        this.atores = new ArrayList<>();
    }
    
    // Getters e Setters
    public String getTitulo() {
        return titulo;
    }
    
    public void setTitulo(String titulo) {
        this.titulo = titulo;
    }
    
    public String getDescricao() {
        return descricao;
    }
    
    public void setDescricao(String descricao) {
        this.descricao = descricao;
    }
    
    public int getAnoLancamento() {
        return anoLancamento;
    }
    
    public void setAnoLancamento(int anoLancamento) {
        this.anoLancamento = anoLancamento;
    }
    
    public List<Ator> getAtores() {
        return atores;
    }
    
    public void setAtores(List<Ator> atores) {
        this.atores = atores;
    }
    
    public void adicionarAtor(Ator ator) {
        atores.add(ator);
    }
}

 classe "Produtora"-------------------------------------------------------------------------
  
  public class Produtora {
    private List<Filme> catalogo;
    
    // Construtor
    public Produtora() {
        this.catalogo = new ArrayList<>();
    }
    
    public void adicionarFilme(Filme filme) {
        catalogo.add(filme);
    }
    
    public void adicionarFilmes(List<Filme> filmes) {
        catalogo.addAll(filmes);
    }
    
    public void exibirCatalogo() {
        for (Filme filme : catalogo) {
            System.out.println("Título: " + filme.getTitulo());
            System.out.println("Descrição: " + filme.getDescricao());
            System.out.println("Ano de Lançamento: " + filme.getAnoLancamento());
            System.out.println("Atores:");
            
            for (Ator ator : filme.getAtores()) {
                System.out.println("- " + ator.getNome());
            }
            
            System.out.println("--------------------------------------");
        }
    }
}
  
CLASSE PRINCIAL --------------------------------------------------------------
  
  public class Main {
    public static void main(String[] args) {
        Produtora produtora = new Produtora();
        
        // Criação de filmes
        Filme filme1 = new Filme("Filme 1", "Descrição do Filme 1", 2022);
        Filme filme2 = new Filme("Filme 2", "Descrição do Filme 2", 2023);
        
        // Criação de atores
        Ator ator1 = new Ator("Ator 1", 4);
        Ator ator2 = new Ator("Ator 2", 5);
        
        // Associação de atores aos filmes
        filme1.adicionarAtor(ator1);
        filme1.adicionarAtor(ator2);
        filme2.adicionarAtor(ator1);
        
        // Adição de filmes ao catálogo da produtora
        produtora.adicionarFilme(filme1);
        produtora.adicionarFilme(filme2);
        
        // Criação de uma lista de filmes
        List<Filme> filmes = new ArrayList<>();
        filmes.add(new Filme("Filme 3", "Descrição do Filme 3", 2024));
        filmes.add(new Filme("Filme 4", "Descrição do Filme 4", 2025));
        
        // Adição da lista de filmes à produtora
        produtora.adicionarFilmes(filmes);
        
        // Exibição das informações de todos os filmes
        produtora.exibirCatalogo();
    }
}

  
