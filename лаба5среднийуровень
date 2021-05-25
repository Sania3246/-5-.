//3 вариант.Дан файл f, компоненты которого являются целыми числами. Получить в файле g все компоненты файла f, являющиеся точными квадратами.
#include <stdlib.h>
#include <stdio.h>
#include <time.h>

int main(int argc, char* argv[])
{
    FILE* fin, * fout;

    int num;
    size_t i;

    switch (argc)
    {
    case 1:
        fprintf(stderr, "Usage: %s FILE [FILE]\n", argv[0]);
        exit(1);
        break;
    case 3:
        fin = fopen(argv[1], "rb");
        fout = fopen(argv[2], "wb");

        while (fread(&num, sizeof(int), 1, fin))
        {
            if (num % 2 == 0)
            {
                if (!fwrite(&num, sizeof(int), 1, fout))
                {
                    perror("fwrite");
                    exit(1);
                }
            }
        }

        if (ferror(fin))
        {
            perror("fread");
            exit(1);
        }
    }

    exit(0);
}
