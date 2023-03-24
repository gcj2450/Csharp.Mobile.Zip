# Csharp.Mobile.Zip
Open source ICSharpCode.SharpZipLib.Zip modified for mobile used by Unity

public static void ExtractTGZ(String gzArchiveName, String destFolder)
    {
        Stream inStream = File.OpenRead(gzArchiveName);
        Stream gzipStream = new GZipInputStream(inStream);

        TarArchive tarArchive = TarArchive.CreateInputTarArchive(gzipStream);
        tarArchive.ExtractContents(destFolder);
        tarArchive.Close();

        gzipStream.Close();
        inStream.Close();
    }
