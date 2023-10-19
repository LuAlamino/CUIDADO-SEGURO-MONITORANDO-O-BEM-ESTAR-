"# CUIDADO-SEGURO-MONITORANDO-O-BEM-ESTAR-" 

public class Main {
    public static void main(String[] args) {

        boolean Escola = true;
        boolean Horario7 = true;
        boolean Natacao = true;
        boolean Horario12 = true;
        boolean Curso = true;
        boolean Horario15 = true;
        boolean EstaNaEscola = Escola && Horario7;
        boolean EstaNaNatacao = Natacao && Horario12;
        boolean EstaNoCurso = Curso && Horario15;



        String escola = Escola ? "Esta Na Escola" : "Não Esta Na Escola";
        String natacao = Natacao ? "Esta Na Natação" : "Não Esta Na Natação";
        String curso = Curso ? "Esta No Curso" : "Não Esta No Curso";

        System.out.println(escola);
        System.out.println(natacao);
        System.out.println(curso);




    }

}
