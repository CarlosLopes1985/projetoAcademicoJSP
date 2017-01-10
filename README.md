# projetoAcademicoJSP

package entity;

public class Pessoa {

	private String nome;
	private String telefone;
	private String celular;
	private String sexo;
	
	public Pessoa() {
		super();
	}

	public Pessoa(String nome, String telefone, String celular, String sexo) {
		super();
		this.nome = nome;
		this.telefone = telefone;
		this.celular = celular;
		this.sexo = sexo;
	}

	public String getNome() {
		return nome;
	}

	public void setNome(String nome) {
		this.nome = nome;
	}

	public String getTelefone() {
		return telefone;
	}

	public void setTelefone(String telefone) {
		this.telefone = telefone;
	}

	public String getCelular() {
		return celular;
	}

	public void setCelular(String celular) {
		this.celular = celular;
	}

	public String getSexo() {
		return sexo;
	}

	public void setSexo(String sexo) {
		this.sexo = sexo;
	}

	@Override
	public String toString() {
		return "Pessoa [nome=" + nome + ", telefone=" + telefone + ", celular=" + celular + ", sexo=" + sexo + "]";
	}
	
	
	
	
}


package entity;

import java.util.ArrayList;
import java.util.List;

public class Aluno extends Pessoa {

	private Integer idAluno;
	private Login login;
	private Endereco endereco;
	private List<Turma>Turma;
	private List<Aluno_Turma>aluno_turma;
	
	public Aluno() {
		super();
	}

	

	public Aluno(Integer idAluno,String nome, String telefone, String celular, String sexo, Endereco endereco) {
		super(nome, telefone, celular, sexo);
		this.idAluno = idAluno;
		this.endereco = endereco;
	}



	public Aluno(Integer idAluno,String nome, String telefone, String celular, String sexo, Login login) {
		super(nome, telefone, celular, sexo);
		this.idAluno = idAluno;
		this.login = login;
	}



	public Aluno(Integer idAluno,String nome, String telefone, String celular, String sexo) {
		super(nome, telefone, celular, sexo);
		this.idAluno = idAluno;
	}



	public Aluno(Integer idAluno,String nome, String telefone, String celular, String sexo,Login login,
			Endereco endereco) {
		super(nome, telefone, celular, sexo);
		this.idAluno = idAluno;
		this.login = login;
	//	this.endereco = endereco;
	}



	@Override
	public String toString() {
		return "Aluno [idAluno=" + idAluno + "]";
	}

	public Integer getIdAluno() {
		return idAluno;
	}

	public void setIdAluno(Integer idAluno) {
		this.idAluno = idAluno;
	}

	public Login getLogin() {
		return login;
	}

	public void setLogin(Login login) {
		this.login = login;
	
	}

	public Endereco getEndereco() {
		return endereco;
	}

	public void setEndereco(Endereco endereco) {
		
		this.endereco = endereco;
	
	}

public List<Turma> getTurma() {
		return Turma;
	}



	public void setTurma(List<Turma> Turma) {
		this.Turma = Turma;
	}



	public List<Aluno_Turma> getAluno_Turma() {
		return aluno_turma;
	}



	public void setAluno_Turma(List<Aluno_Turma> aluno_Turma) {
		this.aluno_turma = aluno_Turma;
	}
	
	
	public void adicionaTurma(Turma m){
		if(Turma==null){
			Turma =new ArrayList<Turma>();
		}if(aluno_turma==null){
			aluno_turma =new ArrayList<Aluno_Turma>();
		}
		Turma.add(m);
		aluno_turma.add(new Aluno_Turma(this, m ) );
	}

}


package entity;

public class Aluno_Turma {

	private Aluno aluno;
	private Turma Turma;
	
	public Aluno_Turma() {
		super();
	}
	public Aluno_Turma(Aluno aluno, Turma Turma) {
		super();
		this.aluno = aluno;
		this.Turma = Turma;
	}
	public Aluno getAluno() {
		return aluno;
	}
	public void setAluno(Aluno aluno) {
		this.aluno = aluno;
	}
	public Turma getTurma() {
		return Turma;
	}
	public void setTurma(Turma Turma) {
		this.Turma = Turma;
	}
	@Override
	public String toString() {
		return "Aluno_Turma [aluno=" + aluno + ", Turma=" + Turma + "]";
	}
}

package entity;

public class Endereco {

	private Integer idEndereco;
	private String logradouro;
	private String numCasa;
	private String estado;
	private String cidade;
	private Aluno aluno;
	
	public Endereco() {
		super();
	}

	public Endereco(Integer idEndereco, String logradouro, String numCasa, String estado, String cidade, Aluno aluno) {
		super();
		this.idEndereco = idEndereco;
		this.logradouro = logradouro;
		this.numCasa = numCasa;
		this.estado = estado;
		this.cidade = cidade;
		this.aluno = aluno;
	}

	public Endereco(Integer idEndereco, String logradouro, String numCasa, String estado, String cidade) {
		super();
		this.idEndereco = idEndereco;
		this.logradouro = logradouro;
		this.numCasa = numCasa;
		this.estado = estado;
		this.cidade = cidade;
	}

	@Override
	public String toString() {
		return "Endereco [idEndereco=" + idEndereco + ", logradouro=" + logradouro + ", numCasa=" + numCasa
				+ ", estado=" + estado + ", cidade=" + cidade + "]";
	}

	public Integer getIdEndereco() {
		return idEndereco;
	}

	public void setIdEndereco(Integer idEndereco) {
		this.idEndereco = idEndereco;
	}

	public String getLogradouro() {
		return logradouro;
	}

	public void setLogradouro(String logradouro) {
		this.logradouro = logradouro;
	}

	public String getNumCasa() {
		return numCasa;
	}

	public void setNumCasa(String numCasa) {
		this.numCasa = numCasa;
	}

	public String getEstado() {
		return estado;
	}

	public void setEstado(String estado) {
		this.estado = estado;
	}

	public String getCidade() {
		return cidade;
	}

	public void setCidade(String cidade) {
		this.cidade = cidade;
	}

	public Aluno getAluno() {
		return aluno;
	}

	public void setAluno(Aluno aluno) {
		this.aluno = aluno;
	}
}

package entity;

public class Login {

	private Integer idLogin;
	private String email;
	private String senha;
	private String perfil;
	private Boolean status;
	

	public Login(Integer idLogin, String email, String senha, String perfil,Boolean status) {

		this.idLogin = idLogin;
		this.email = email;
		this.senha = senha;
		this.perfil = perfil;
		this.status = status;
	}

	public Login() {
		this.status = true; 
	}

	@Override
	public String toString() {
		return "Login [idLogin=" + idLogin + ", email=" + email + ", perfil=" + perfil + ", status=" + status +"]";
	}

	public Integer getIdLogin() {
		return idLogin;
	}

	public void setIdLogin(Integer idLogin) {
		this.idLogin = idLogin;
	}

	public String getEmail() {
		return email;
	}

	public void setEmail(String email) {
		this.email = email;
	}

	public String getSenha() {
		return senha;
	}

	public void setSenha(String senha) {
		this.senha = senha;
	}

	public String getPerfil() {
		return perfil;
	}

	public void setPerfil(String perfil) {
		this.perfil = perfil;
	}

	public Boolean getStatus() {
		return status;
	}

	public void setStatus(Boolean status) {
		this.status = status;
	}

}

package entity;

import java.util.Date;

public class Medidas {

	private Integer idMedidas;
	private Double peso;
	private Double altura;
	private Double imc;
	private Date dataMedida;
	private Aluno aluno;

	public Medidas() {

	}

	

	public Medidas(Integer idMedidas, Double peso, Double altura, Double imc, Date dataMedida, Aluno aluno) {
		super();
		this.idMedidas = idMedidas;
		this.peso = peso;
		this.altura = altura;
		this.imc = imc;
		this.dataMedida = dataMedida;
		this.aluno = aluno;
	}

   

	@Override
	public String toString() {
		return "Medidas [idMedidas=" + idMedidas + ", peso=" + peso + ", altura=" + altura + ", imc=" + imc
				+ ", dataMedida=" + dataMedida + "]";
	}

	public Medidas(Integer idMedidas, Double peso, Double altura, Double imc, Date dataMedida) {
	
		this.idMedidas = idMedidas;
		this.peso = peso;
		this.altura = altura;
		this.imc = imc;
		this.dataMedida = dataMedida;
	}



	public Integer getIdMedidas() {
		return idMedidas;
	}

	public void setIdMedidas(Integer idMedidas) {
		this.idMedidas = idMedidas;
	}

	public Double getPeso() {
		return peso;
	}

	public void setPeso(Double peso) {
		this.peso = peso;
	}

	public Double getAltura() {
		return altura;
	}

	public void setAltura(Double altura) {
		this.altura = altura;
	}

	public Double getImc() {
		return imc;
	}

	public void setImc(Double imc) {
		this.imc = imc;
	}

	public Aluno getAluno() {
		return aluno;
	}

	public void setAluno(Aluno aluno) {
		this.aluno = aluno;
	}



	public Date getDataMedida() {
		return dataMedida;
	}



	public void setDataMedida(Date dataMedida) {
		this.dataMedida = dataMedida;
	}
}

package entity;

import java.io.Serializable;
import java.util.List;

public class Turma implements Serializable {
	
	/**
	 * 
	 */
	private static final long serialVersionUID = 1L;
	private Integer idTurma;
	private String nomeTurma;
	private Integer cargaHoraria;
	private String horario;
	private Double preco;
	
	private List<Aluno>aluno;

	public Turma() {
		super();
	}

	public Turma(Integer idTurma, String nomeTurma, Integer cargaHoraria, String horario, Double preco,
			List<Aluno> aluno) {
		super();
		this.idTurma = idTurma;
		this.nomeTurma = nomeTurma;
		this.cargaHoraria = cargaHoraria;
		this.horario = horario;
		this.preco = preco;
		this.aluno = aluno;
	}

	public Turma(Integer idTurma, String nomeTurma, Integer cargaHoraria, String horario, Double preco) {
		super();
		this.idTurma = idTurma;
		this.nomeTurma = nomeTurma;
		this.cargaHoraria = cargaHoraria;
		this.horario = horario;
		this.preco = preco;
	}

	@Override
	public String toString() {
		return "Turma [idTurma=" + idTurma + ", nomeTurma=" + nomeTurma + ", cargaHoraria=" + cargaHoraria
				+ ", horario=" + horario + ", preco=" + preco + "]";
	}

	public Integer getIdTurma() {
		return idTurma;
	}

	public void setIdTurma(Integer idTurma) {
		this.idTurma = idTurma;
	}

	public String getNomeTurma() {
		return nomeTurma;
	}

	public void setNomeTurma(String nomeTurma) {
		this.nomeTurma = nomeTurma;
	}

	public Integer getCargaHoraria() {
		return cargaHoraria;
	}

	public void setCargaHoraria(Integer cargaHoraria) {
		this.cargaHoraria = cargaHoraria;
	}

	public String getHorario() {
		return horario;
	}

	public void setHorario(String horario) {
		this.horario = horario;
	}

	public Double getPreco() {
		return preco;
	}

	public void setPreco(Double preco) {
		this.preco = preco;
	}

	public List<Aluno> getAluno() {
		return aluno;
	}

	public void setAluno(List<Aluno> aluno) {
		this.aluno = aluno;
	}

	public static long getSerialversionuid() {
		return serialVersionUID;
	}
	
	
}
_______________________________________________________________________________________________________________________________

package persistence;


import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.util.ArrayList;
import java.util.List;

import entity.Aluno;
import entity.Turma;

public class AlunoDao extends Dao {

	public void create(Aluno a) throws Exception {
		open();

		stmt = con.prepareStatement("insert into aluno values(null,?,?,?,?,?,?)");
		stmt.setString(1, a.getNome());
		stmt.setString(2, a.getTelefone());
		stmt.setString(3, a.getCelular());
		stmt.setString(4, a.getSexo());
		stmt.setInt(5, a.getLogin().getIdLogin());
		stmt.setInt(6, a.getEndereco().getIdEndereco());
		stmt.execute();
		close();
	}
	
	public String consultaNome( int idAluno ) throws Exception{
	
		open();
		
		String nome = "";
		
		stmt = con.prepareStatement("select nome from aluno where idAluno = ? ");
		stmt.setInt(1, (idAluno) );
		
		rs = stmt.executeQuery();
		
		if( rs.next( ) )
			nome = rs.getString("nome");

		return nome;
	}
	
	public void deletarAluno( int idAluno ) throws Exception{
		open( );
		
		stmt = con.prepareStatement( "delete from aluno where idAluno = ?" );
		stmt.setInt(1, (idAluno));
		
		stmt.execute();
		close();
		}
	/*
	 * Altera status do aluno, aluno só terá acesso ao sistema caso seu staus seja ativo
	 * @Param status
	 * @Param idAluno 
	 */
	public void updateStatus( boolean status, int idAluno )throws Exception{
		
		open( );
		
		stmt =  con.prepareStatement( "update Login set status = ? where idLogin = ? ");
		
		stmt.setBoolean(1, ( status ) );
		stmt.setInt(2, (idAluno));
		stmt.execute();
		
		close();
		}
	
	
	/*
	 * Lista todos os alunos do sistema
	 */
	public List<Aluno> findAll() throws Exception {
		open();

		stmt = con.prepareStatement("select * from aluno");
		rs = stmt.executeQuery();
		List<Aluno> lista = new ArrayList<>();
		while (rs.next()) {
			lista.add(new Aluno(rs.getInt(1), rs.getString(2), rs.getString(3), rs.getString(4), rs.getString(5)));

		}

		close();
		return lista;
	}
	
	
	/*
	 * Lista todos os alunos e turmas 
	 */
	public List<Aluno> findAllcomTurma() throws Exception {
		open();

		stmt = con.prepareStatement("select * from aluno");
		rs = stmt.executeQuery();
		List<Aluno> lista = new ArrayList<>();
		while (rs.next()) {
			Aluno a = new Aluno();
			a.setIdAluno(rs.getInt("idAluno"));
			a.setNome(rs.getString("nome"));
			a.setTelefone(rs.getString("telefone"));
			a.setCelular(rs.getString("celular"));
			a.setSexo("sexo");
			

			PreparedStatement stmt2 = con.prepareStatement(
					"select * from turma inner join aluno_turma on idTurma = turma_idTurma where aluno_idAluno = ? ");

			stmt2.setInt(1, rs.getInt("idAluno"));
			ResultSet rs2 = stmt2.executeQuery();
			while (rs2.next()) {

				Turma t = new Turma();

				t.setIdTurma(rs2.getInt("idTurma"));

				t.setNomeTurma(rs2.getString("nomeTurma"));

				t.setCargaHoraria(rs2.getInt("cargaHr"));
				
				a.adicionaTurma(t);

			}

			stmt2.close();

			rs2.close();

			lista.add(a);

		}

		stmt.close();

		rs.close();

		close();

		return lista;

	}

	public static void main(String[] args) {
		try {
			
		
		AlunoDao ad = new AlunoDao();

		ad.updateStatus(true, 3);
		
//		ad.deletarAluno(1);
//		
//		String aluno = ad.consultaNome(1);
//		
		System.out.println("aluno alterado com sucesso!!!");
		
		} catch (Exception e) {
			e.printStackTrace();
			System.out.println(e.getMessage());
		}
	}
	
}


package persistence;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;

public class Dao {

	Connection con;
	ResultSet rs;
	PreparedStatement stmt;
	
	public void open( )throws Exception{
		
		Class.forName("com.mysql.jdbc.Driver");
		con = DriverManager.getConnection
				("jdbc:mysql://localhost:3306/projetoAcademico","root","371casa1");
	}
	
	public void close( )throws Exception{
		con.close();
	}
	
	public static void main(String[] args) {
		
		try {
			Dao d = new Dao();
			d.open();
			d.close();
			System.out.println("Aberta com sucesso!!!");
		} catch (Exception e) {
			System.out.println("Deu merda!!!");
		}
		
	}
}


package persistence;

import com.mysql.jdbc.PreparedStatement;

import entity.Aluno;
import entity.Endereco;

public class EnderecoDao extends Dao {

	public int createEndereco( Endereco e )throws Exception{
		
		open();
		
		stmt = con.prepareStatement("insert into endereco values(null,?,?,?,?)",
				PreparedStatement.RETURN_GENERATED_KEYS);
		stmt.setString(1, e.getLogradouro());
		stmt.setString(2, e.getNumCasa());
		stmt.setString(3, e.getEstado());
		stmt.setString(4, e.getCidade());
		stmt.execute();
		
		rs = stmt.getGeneratedKeys();
		rs.next();
		e.setIdEndereco(rs.getInt(1));
		
		close();
		
		return e.getIdEndereco();
	}
	
public static void main(String[] args) {
		
		try {
			
			Endereco a = new Endereco(null,"rua jururena","335","RJ","RIO selvagem");
			new EnderecoDao().createEndereco(a);
			System.out.println("Dados gravados");
			
		} catch (Exception e) {
			// TODO: handle exception
			e.printStackTrace();
		}
}
}


package persistence;

import java.sql.PreparedStatement;

import entity.Login;

public class LoginDao extends Dao {
	
	public int createLogin( Login l )throws Exception{
		open();
		
		stmt = con.prepareStatement("insert into login values( null,?,?,?,?)"
				,PreparedStatement.RETURN_GENERATED_KEYS);
		stmt.setString(1, l.getEmail( ) );
		stmt.setString(2, l.getSenha( ) );
		stmt.setString(3, l.getPerfil( ) );
		stmt.setBoolean(4, l.getStatus( ) );
		stmt.execute();
		
		rs = stmt.getGeneratedKeys(); //retornando a chave..

		rs.next(); //ativar a leitura dos dados..

		l.setIdLogin(rs.getInt(1)); //posição da chave...

		close(); 
		return l.getIdLogin(); //retornando a chave..
	}
	
	public Login findByLogin( Login l )throws Exception{
		open();
		
		stmt = con.prepareStatement("select * from login l where email= ? and senha= ? and status = ?");
		stmt.setString(1, l.getEmail( ) );
		stmt.setString(2, l.getSenha( ) );
		stmt.setBoolean(3, l.getStatus( ) );
		
		rs = stmt.executeQuery();
		
		Login login = null;
		
		 boolean b = l.getStatus();
		 
		 if( b == false ){
		    login = null;	 
		 }
		
		else if(rs.next( ) ){
			login = new Login();
			login.setIdLogin( rs.getInt   ( 1 ) );
			login.setEmail  ( rs.getString( 2 ) );
			login.setSenha  ( rs.getString( 3 ) );
			login.setPerfil ( rs.getString( 4 ) );
			login.setStatus ( rs.getBoolean( 5 ) );
		}
		stmt.close();

		close();

		return login; //null (quando nao encontra) ou cheio
	}

	public static void main(String[] args) {
		
		try {
			
			Login l = new Login( );
			l.setEmail("caka50@hotmail.com");
			l.setSenha("123");
			l.setPerfil("administrador");
			
		Login resp =	new LoginDao().findByLogin(l);
		
		System.out.println(resp);

			if (resp!=null){

				System.out.println("Logado :" + resp);
			}else{

				System.out.println("...Nao Logado...");

				}
			
		} catch (Exception e) {
			
			System.out.println("Fez merda animal!!!"+e.getMessage( ) );
			e.printStackTrace();
		}
	}
	
}


package persistence;

import java.sql.Date;
import java.util.ArrayList;
import java.util.List;

import entity.Aluno;
import entity.Medidas;

public class MedidasDao extends Dao {

	public void cadastrarMedidas(Medidas ma, Aluno a) throws Exception {
		open();

		stmt = con.prepareStatement("insert into medidas_aluno values(null,?,?,?,?,?)");
		stmt.setDouble(1, ma.getPeso());
		stmt.setDouble(2, ma.getAltura());
		stmt.setDouble(3, ma.getImc());
		java.sql.Timestamp data =

				new java.sql.Timestamp(ma.getDataMedida().getTime());

				stmt.setTimestamp(4, data);
	//	stmt.setDate(4,new Date( ma.getDataMedida( ).getTime( ) ) );
		stmt.setInt(5, a.getIdAluno( ) );
		stmt.execute();
		close();
	}
	
	public List<Medidas> findAll() throws Exception {
		open();

		stmt = con.prepareStatement("select * from medidas_aluno");
		rs = stmt.executeQuery();
		List<Medidas> lista = new ArrayList<>();
		while (rs.next()) {
			lista.add(new Medidas(rs.getInt(1), 
					                   rs.getDouble(2), 
					                   rs.getDouble(3), 
					                   rs.getDouble(4),
					                   rs.getDate(5)));

		}

		close();
		return lista;
	}

	public void alterarMedidas(Medidas ma) throws Exception {
		try {

			open();

			stmt = con.prepareStatement("update medidas_Aluno set peso = ?, altura = ?, imc = ? where idMedidas = ?)");

			stmt.setDouble(1, ma.getPeso());
			stmt.setDouble(2, ma.getAltura());
			stmt.setDouble(3, ma.getImc());
			stmt.setInt(4, ma.getIdMedidas());

			stmt.execute();
			close();
		} catch (Exception e) {
		  System.out.println(e.getMessage() );
		  e.printStackTrace();
		}
	}
}



package persistence;
import java.util.ArrayList;
import java.util.List;

import entity.Aluno;
import entity.Turma;

public class TurmaDao extends Dao {

	public void createTurma(Turma t)throws Exception{
		open();
		
		stmt = con.prepareStatement("insert into turma values(null,?,?,?,?)");
		stmt.setString (1, t.getNomeTurma());
		stmt.setInt    (2, t.getCargaHoraria());
		stmt.setString (3,t.getHorario());
		stmt.setDouble (4, t.getPreco());
		stmt.execute();
		close();
	}

	public List<Turma> findAll() throws Exception {
		open();
		stmt = con.prepareStatement("select * from turma");
		rs = stmt.executeQuery();
		List<Turma> lista = new ArrayList<>();
		while (rs.next()) {
			lista.add(new Turma(rs.getInt(1), 
					rs.getString(2), 
					rs.getInt(3), 
					rs.getString(4), 
					rs.getDouble(5))
					);
		}
		close();
		return lista;
	}
	
	public Turma findByCode(Integer cod)throws Exception{
		open();
		stmt = con.prepareStatement("select * from turma where idTurma=? ");
		stmt.setInt(1, cod);
		Turma t = null;
		rs = stmt.executeQuery();
		if(rs.next()){
			t = new Turma(rs.getInt(1), 
					rs.getString(2), 
					rs.getInt(3), 
					rs.getString(4), 
					rs.getDouble(5)
					);
			}
		close();
		return t;
	}
	
	public void alocar(Turma t, Aluno a)throws Exception{
		open();
		stmt = con.prepareStatement("insert into aluno_turma values(?,?)");
		stmt.setInt(1, a.getIdAluno());
		stmt.setInt(2, t.getIdTurma());
		stmt.execute();
		close();
		
	}
		
	
}


create database projetoAcademico;
use projetoAcademico;

create table login(
	idLogin int auto_increment primary key,
	email varchar(50),
	senha varchar(100),
	perfil varchar(50)
);
alter table login add status boolean

create table endereco(
	idEndereco int auto_increment primary key,
	logradouro varchar(100),
	numero varchar(30),
	estado  varchar(50),
	cidade varchar(30)
	);

alter table aluno add constraint id_endereco foreign key(id_endereco) references endereco(idEndereco); 

create table aluno(
	idAluno int auto_increment primary key,
	nome     varchar(50),
	telefone varchar(30),
	celular  varchar(30),
	sexo     varchar(15),
	id_login int not null unique,
	id_endereco int not null unique,
foreign key(id_login)references login(idLogin)

);

create table turma(
	idTurma int auto_increment primary key,
	nomeTurma varchar(30),
	cargaHoraria int, 
	horario varchar(30),
	preco double
);

create table aluno_turma(
	aluno_idAluno int,
	turma_idTurma int,
	primary key(aluno_idAluno,turma_idTurma),
	foreign key(aluno_idAluno)references aluno(idAluno),
	foreign key(turma_idTurma)references turma(idTurma)
	
);

create table medidas_aluno(
	idMedidas int primary key auto_increment,
	peso double,
	altura double,
	imc double,
	dataMedida date,
	id_Aluno int not null,
	foreign key(id_Aluno)references Aluno(idAluno)
);

select a.id_login, l.idLogin,a.nome, l.email from aluno a inner join login l on l.idLogin = a.id_Login;

insert into login values(null,"bete@hotmail.com","371casa1","usuario");
select * from login l where email="caka19_rj@hotmail.com" and senha="123" and status=1;





package manager;

import java.util.List;

import entity.Aluno;
import entity.Turma;
import persistence.AlunoDao;
import persistence.TurmaDao;

public class ManagerBean {

	private List<Aluno>listaAluno;
	private List<Turma>listaTurma;
	private List<Aluno>listaAlunoTurma;
	
	public List<Aluno>getListaAluno(){
		try {
			listaAluno = new AlunoDao().findAll();
		} catch (Exception e) {
			e.printStackTrace();
		}
		return listaAluno;
	}

	public void setListaAluno(List<Aluno> listaAluno) {
		this.listaAluno = listaAluno;
	}

	public List<Turma> getListaTurma() {
		try {
			listaTurma = new TurmaDao().findAll();
		} catch (Exception e) {
			e.printStackTrace();
		}
		
		return listaTurma;
	}

	public void setListaTurma(List<Turma> listaTurma) {
		this.listaTurma = listaTurma;
	}

	public List<Aluno> getListaAlunoTurma() {
		try {
			listaAlunoTurma = new AlunoDao().findAllcomTurma();
		} catch (Exception e) {
		e.printStackTrace();
		}
		
		return listaAlunoTurma;
	}

	public void setListaAlunoTurma(List<Aluno> listaAlunoTurma) {
		this.listaAlunoTurma = listaAlunoTurma;
	}
	
	
	
}


package control;

import java.io.IOException;
import java.text.DateFormat;
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;


import entity.Aluno;
import entity.Endereco;
import entity.Login;
import entity.Medidas;
import entity.Turma;
import persistence.AlunoDao;
import persistence.EnderecoDao;
import persistence.LoginDao;
import persistence.MedidasDao;
import persistence.TurmaDao;


@WebServlet("/Controle")
public class Controle extends HttpServlet {
	private static final long serialVersionUID = 1L;

   

	
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		
	}

	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		
		String cmd = request.getParameter("cmd");
		if(cmd.equalsIgnoreCase("logar")){
		logar(request,response);
		}else if(cmd.equalsIgnoreCase("gravar")){
			gravar(request,response);
		}else if(cmd.equalsIgnoreCase("gravarTurma")){
			gravarTurma(request,response);
	    }else if(cmd.equalsIgnoreCase("alocar")){
		alocar(request,response);
	    }else if(cmd.equalsIgnoreCase("cadastrarMedidas")){
	    	cadastrarMedidas(request,response);
	    }
	}
	

	
	private void cadastrarMedidas(HttpServletRequest request, HttpServletResponse response)throws ServletException, IOException {
		
	String msg = "";
 
			try {

				Integer idAluno = new Integer(request.getParameter("idAluno"));
				Aluno a = new Aluno();
				a.setIdAluno(idAluno);

				Medidas md = new Medidas();
				md.setPeso(Double.parseDouble(request.getParameter("peso")));
				md.setAltura(Double.parseDouble(request.getParameter("altura")));
				
				DataFormate df = new DataFormate();
				
		        Date data = df.converte(request.getParameter("dataMedida"));
//				SimpleDateFormat formato = new SimpleDateFormat("yyyy-MM-dd");
//				Date data = formato.parse(request.getParameter("dataMedida"));
			//	data.applyPattern("MM/dd/yyyy");
				
				//String dataFormatada = formato.format(data);
				
				System.out.println(data);
	            md.setDataMedida(data);
	           
				
				md.setImc(md.getPeso() /( md.getAltura() * md.getAltura()));
			
				md.setImc(md.getImc());
				md.setAluno(a);

				MedidasDao mad = new MedidasDao();

				mad.cadastrarMedidas(md, a);

				
				msg = "Medidas cadastradas com Sucesso!!! Seu IMC é " + md.getImc();

			} catch (Exception e) {

				e.printStackTrace();
				System.out.println(e.getMessage());
				msg = "Não cadastrados";

			} finally {
				request.setAttribute("msg", msg);
				request.getRequestDispatcher("cadastrarMedidas.jsp").forward(request, response);

			}

	}

	private void alocar(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		
		String msg ="";
		
		try {
			
			Integer idAluno = new Integer(request.getParameter("idAluno"));
			Integer idTurma = new Integer(request.getParameter("idTurma"));
			
			Aluno a = new Aluno();
			a.setIdAluno(idAluno);
			
			Turma t = new Turma();
			t.setIdTurma(idTurma);
			
			new TurmaDao().alocar(t,a);
			
			msg="matricula realizada com sucesso";
			
		} catch (Exception e) {
			e.printStackTrace();
			System.out.println(e.getMessage());
			msg="Matricula não realizada... Verifique se o aluno já não esta "
					+ "cadatsrado em uma turma!!!";
		}finally{
			request.setAttribute("msg", msg);
			request.getRequestDispatcher("alocarAluno.jsp").
			forward(request, response);
		}

		
	}

	private void gravarTurma(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		try {
			Turma t = new Turma();
			TurmaDao td = new TurmaDao();
			
			t.setNomeTurma(request.getParameter("modalidade"));
			t.setCargaHoraria(Integer.parseInt(request.getParameter("cargaHoraria")));
			t.setHorario(request.getParameter("horario"));
			t.setPreco(Double.parseDouble(request.getParameter("preco")));
			
			td.createTurma(t);
			
		} catch (Exception e) {
			e.printStackTrace();
			System.out.println(e.getMessage());
		}finally{
			request.getRequestDispatcher("cadastrarTurmas.jsp").forward(request, response);
		}
		
	}

	private void gravar(HttpServletRequest request, HttpServletResponse response) 
			throws ServletException, IOException{
		
		try {
			
			Login l = new Login();
			Aluno a = new Aluno();
			Endereco e = new Endereco();
			LoginDao ld = new LoginDao();
			AlunoDao ad = new AlunoDao();
			EnderecoDao ed = new EnderecoDao();
			
			l.setEmail(request.getParameter("email"));
			l.setSenha(request.getParameter("senha"));
			l.setPerfil(request.getParameter("perfil"));
			
			
			
			a.setNome(request.getParameter("nome"));
			a.setTelefone(request.getParameter("telefone"));
			a.setCelular(request.getParameter("celular"));
			a.setSexo(request.getParameter("sexo"));
			a.setLogin(l);
		
			e.setLogradouro(request.getParameter("logradouro"));
			e.setNumCasa(request.getParameter("numCasa"));
			e.setCidade(request.getParameter("cidade"));
			e.setEstado(request.getParameter("estado"));
			
			a.setEndereco(e);
			
			ld.createLogin(l);
			System.out.println(l);
			ed.createEndereco(e);
			System.out.println(e);
			ad.create(a);
			System.out.println(a);
			
			request.setAttribute("msg", "Dados gravados!!!");
			
			
		} catch (Exception e) {
			request.setAttribute("msg", e.getMessage( ) );
		}finally{
			request.getRequestDispatcher("cadastro.jsp").forward(request, response);
		}
		
	}

	private void logar(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		
		String email = request.getParameter("email");
		String senha = request.getParameter("senha");
		
	//	HttpSession session = null;
		
		try {
			Login l = new Login();
			l.setEmail(email);
			l.setSenha(senha);
//			session = request.getSession(true);
			
			LoginDao ld = new LoginDao();
			Login resp = new LoginDao().findByLogin(l);
			
			if(resp == null){
				request.setAttribute("msg", "Usuario inválido!!!");
				request.getRequestDispatcher("sistema.jsp").forward(request, response);
			}
			
		else if(resp!=null){
				if(resp.getPerfil( ).equalsIgnoreCase("usuario") ){
					request.setAttribute("msg", "Usuario Logado com sucesso!!!");
					//session.setAttribute( "usuario",resp );
					request.getRequestDispatcher("usuario/logado.jsp").
					forward(request, response);
					}else if(resp.getPerfil().equalsIgnoreCase( "administrador" ) ){
						request.setAttribute("msg", "Administrador Logado com sucesso!");
						//session.setAttribute( "usuario",resp );
						request.getRequestDispatcher("administrador/logado.jsp").forward(request, response);
					}else{
						//session.setAttribute( "usuario",resp );
						request.setAttribute("msg", "Usuario inválido!!!");
						request.getRequestDispatcher("sistema.jsp").forward(request, response);
					}
			}
		} catch (Exception e) {
			// TODO: handle exception
			e.printStackTrace();
			System.out.println(e.getMessage());
		}finally{
			request.getRequestDispatcher("login.jsp").forward(request, response);
		}
		
	}

}



package control;

import java.text.SimpleDateFormat;
import java.util.Date;

public class DataFormate {


	public Date converte ( String data  ) throws Exception{
		
		SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd");
		
		Date Data = sdf.parse( data ); 
		
		return Data;
	}
}



<!DOCTYPE html>
<html>
<head>
<link href="bootstrap/css/bootstrap.css" rel="stylesheet" type="text/css"/>

<script type="bootstrap/text/javascript" src="js/jquery.js"></script>

<script type="bootstrap/text/javascript" src="js/bootstrap.js"></script>

<script type="text/javascript">
	
	function validaLogin(){
		if(document.formLogin.email.value==""){
			alert("Campo de usuário não informado!!!");
			return false;
		}
		if(document.formLogin.senha.value==""){
			alert("Campo de senha não informado!!!");
			return false;
		}
		
		document.formLogin.submit();
	}

</script>

</head>
<body>
	<div class="container">
		<div class="well">
		<h1>Login com JSP</h1>
	</div>
	
	<div class="col-sm-8 col-sm-offset-1">
		<form name="formLogin" method="post" action="Controle?cmd=logar">
		<b>Logar com os dados:</b>
		<br/></br>Email:</br>
		
		<input type="text" name="email" size="50" value="" placeholder="Digite seu email"/>
		
		<br/></br>Senha:</br>
		<input type="password" name="senha" size="50" value="" placeholder="Digite sua senha"/>
		<br/></br>
		
		<input type="button" value="Enviar os Dados" onclick="validaLogin()"/>
		<br>
		<strong>${msg}</strong>
		</form>
		
		</div>
	</div>


</body>
</html>



<!DOCTYPE html>
<html>
<head>
<link href="bootstrap/css/bootstrap.css" rel="stylesheet" type="text/css"/>

<script type="bootstrap/text/javascript" src="js/jquery.js"></script>

<script type="bootstrap/text/javascript" src="js/bootstrap.js"></script>

<script type="text/javascript"> </script>

</head>
<body>
	<div class="container">
		<div class="well">
		<h1>Cadastrar Aluno Academia do Corpo</h1>
	</div>
	
	<div class="col-sm-8 col-sm-offset-1">
	<form name="formCadastro" method="post" action="Controle?cmd=gravar">
	
		<b>Gravar Dados:</b>
		
		<br/></br>Email:</br>
		<input type="text" id="email" name="email" size="50" value="" placeholder="Digite seu email"/>
		
		<br><b>Senha:</b></br>
		<input type="password" id="senha" name="senha" size="50" value="" placeholder="Digite sua senha"/>
		
		<br>Perfil:</br>
		<input type="text" id="perfil" name="perfil" size="50" value="" placeholder="Digite sua senha"/>
		
		<br>Nome:</br>
		<input type="text" id="nome" name="nome" size="50" value="" placeholder="Digite sua senha"/>
		
		<br>Telefone:</br>
		<input type="text" id="telefone" name="telefone" size="50" value="" placeholder="Digite sua senha"/>
		
		<br>Celular:</br>
		<input type="text" id="celular" name="celular" size="50" value="" placeholder="Digite sua senha"/>
		
		<br>Sexo:</br>
		<input type="text" id="sexo" name="sexo" size="50" value="" placeholder="Digite sua senha"/>
		
		
		<br>Logradouro:</br>
		<input type="text" id="logradouro" name="logradouro" size="50" value="" placeholder="Digite sua senha"/>
		
		
		<br>Numero Casa:</br>
		<input type="text" id="numCasa" name="numCasa" size="50" value="" placeholder="Digite sua senha"/>
		
		
		<br>Estado:</br>
		<input type="text" id="estado" name="estado" size="50" value="" placeholder="Digite sua senha"/>
		
		<br>Cidade:</br>
		<input type="text" id="cidade" name="cidade" size="50" value="" placeholder="Digite sua senha"/>
		
		<br></br>
		<input type="submit" id="btncadastro" value="CadastrarCliente" class="btn btn-success btn-block"/>
		
		</form>
		
		</div>
	</div>


</body>
</html>


<!DOCTYPE html>
<html>
<head>
<link href="bootstrap/css/bootstrap.css" rel="stylesheet" type="text/css"/>

<script type="bootstrap/text/javascript" src="js/jquery.js"></script>

<script type="bootstrap/text/javascript" src="js/bootstrap.js"></script>

<script type="text/javascript"> </script>

</head>
<body>
	<div class="container">
		<div class="well">
		<h1>Cadastro de Turmas - Academia do Corpo</h1>
	</div>
	
	<div class="col-sm-8 col-sm-offset-1">
	<form name="formCadastro" method="post" action="Controle?cmd=gravarTurma">
	
		<b>Gravar Dados:</b>
		
		<br/></br>Modalidade:</br>
		<input type="text" id="modalidade" name="modalidade" size="50" value="" placeholder="Digite a modalidade"/>
		
		<br>CargaHoraria:</br>
		<input type="number" id="cargaHoraria" name="cargaHoraria" size="50" value="" placeholder="Digite a carga horaria"/>
		
		<br>Horario:</br>
		<input type="text" id="horario" name="horario" size="50" value="" placeholder="Digite o horario"/>
		
		<br>Preço:</br>
		<input type="number" id="preco" name="preco" size="50" value="" placeholder="Digite o preço da turma"/>
		
		
		<br></br>
		<input type="submit" id="btncadastro" value="CadastrarTurma" class="btn btn-success btn-block"/>
		
		</form>
		
		</div>
	</div>


</body>
</html>

<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
    
 <%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
	<jsp:useBean class="manager.ManagerBean" id="mb"/>
    


<!DOCTYPE html>
<html>
<head>
<link href="bootstrap/css/bootstrap.css" rel="stylesheet" type="text/css"/>

<script type="bootstrap/text/javascript" src="js/jquery.js"></script>

<script type="bootstrap/text/javascript" src="js/bootstrap.js"></script>

<script type="text/javascript"> </script>

</head>
<body>
	<div class="container">
		<div class="well">
		<h1>Cadastrar medidas aluno</h1>
	</div>
	<div class="panel-heading">
						<div class="panel-title">
							Cadastrar Medidas Aluno
						</div><!-- FECHA PANEL-TITLE -->
					</div><!-- FECHA PANEL HEADING -->
	<div class="panel-body">
	<form name="formCadastro" method="post" action="Controle?cmd=cadastrarMedidas">

					
	Aluno:<select name ="idAluno" class="form-control">
	<option value="0" selected="selected"> Selecione o aluno</option>
	
	<c:forEach items="${mb.listaAluno}" var="linha">
	
	<option value="${linha.idAluno}"> ${linha.nome} </option>
	</c:forEach>
	</select>
	<br/>
	Peso:
	<input type="decimal" value="" id="peso" name="peso" placeholder="Digite seu peso" />
		<br></br>
	Altura:
	<input type="decimal" value="" id="altura" name="altura" placeholder="Digite sua altura" />
		<br></br>		
	
	Data:
	<input type="date" value="" id="dataMedida" name="dataMedida" placeholder="Digite Data Atual" />
		<br></br>			
						
<button type="submit" class="btn btn-primary">
<span class="glyphicon glyphicon-floopy-disk"></span>
			Cadastrar medidas
</button>

<button type="submit" class="btn btn-primary">
<span class="glyphicon glyphicon-floopy-disk"></span>
			Voltar
</button>
			

			
						
<br/>
<strong>${msg}</strong>
</form>
	</div>

	</div>



</body>
</html>

<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
    
 <%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
	<jsp:useBean class="manager.ManagerBean" id="mb"/>
    


<!DOCTYPE html>
<html>
<head>
<link href="bootstrap/css/bootstrap.css" rel="stylesheet" type="text/css"/>

<script type="bootstrap/text/javascript" src="js/jquery.js"></script>

<script type="bootstrap/text/javascript" src="js/bootstrap.js"></script>

<script type="text/javascript"> </script>

</head>
<body>
	<div class="container">
		<div class="well">
		<h1>Alocação de alunos em turmas</h1>
	</div>
	<div class="panel-heading">
						<div class="panel-title">
							Matricular Aluno na Turma
						</div><!-- FECHA PANEL-TITLE -->
					</div><!-- FECHA PANEL HEADING -->
	<div class="panel-body">
<form method="post" action="Controle" role="form">
<input type="hidden" name="cmd" value="alocar">
					
	Aluno:<select name ="idAluno" class="form-control">
	<option value="0" selected="selected"> Selecione o aluno</option>
	
	<c:forEach items="${mb.listaAluno}" var="linha">
	
	<option value="${linha.idAluno}"> ${linha.nome} </option>
	</c:forEach>
	</select>
	
	Turma: <select name="idTurma" class="form-control">
	<option value="0" selected="selected">Selecione a Turma</option>
	
	<c:forEach items="${mb.listaTurma}" var="linha">
	<option value="${linha.idTurma}"> ${linha.nomeTurma} </option>
	</c:forEach>	
	
	
	</select>
	
	<br/>
						
<button type="submit" class="btn btn-primary">
<span class="glyphicon glyphicon-floopy-disk"></span>
			Alocar Aluno
</button>
						
<br/>
<strong>${msg}</strong>
	</form>
	</div>

	</div>



</body>
</html>
