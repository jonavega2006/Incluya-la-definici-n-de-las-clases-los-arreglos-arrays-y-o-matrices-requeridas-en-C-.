using System;

namespace RegistroEstudiante
{
    // Clase Estudiante
    class Estudiante
    {
        public string Id { get; set; }
        public string Nombres { get; set; }
        public string Apellidos { get; set; }
        public string Direccion { get; set; }
        public string[] Telefonos { get; set; }

        // Método para mostrar la información del estudiante
        public void MostrarDatos()
        {
            Console.WriteLine("\n--- DATOS DEL ESTUDIANTE ---");
            Console.WriteLine("ID: " + Id);
            Console.WriteLine("Nombres: " + Nombres);
            Console.WriteLine("Apellidos: " + Apellidos);
            Console.WriteLine("Dirección: " + Direccion);

            Console.WriteLine("Teléfonos:");
            for (int i = 0; i < Telefonos.Length; i++)
            {
                Console.WriteLine($"  Teléfono {i + 1}: {Telefonos[i]}");
            }
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            Estudiante estudiante = new Estudiante();

            // Ingreso de datos del estudiante
            Console.Write("Ingrese el ID del estudiante: ");
            estudiante.Id = Console.ReadLine();

            Console.Write("Ingrese los nombres del estudiante: ");
            estudiante.Nombres = Console.ReadLine();

            Console.Write("Ingrese los apellidos del estudiante: ");
            estudiante.Apellidos = Console.ReadLine();

            Console.Write("Ingrese la dirección del estudiante: ");
            estudiante.Direccion = Console.ReadLine();

            // Ingreso de teléfonos usando un array
            Console.Write("¿Cuántos números de teléfono desea registrar?: ");
            int cantidadTelefonos = int.Parse(Console.ReadLine());

            estudiante.Telefonos = new string[cantidadTelefonos];

            for (int i = 0; i < cantidadTelefonos; i++)
            {
                Console.Write($"Ingrese el teléfono #{i + 1}: ");
                estudiante.Telefonos[i] = Console.ReadLine();
            }

            // Mostrar datos
            estudiante.MostrarDatos();

            Console.WriteLine("\nPresione una tecla para finalizar...");
            Console.ReadKey();
        }
    }
}
