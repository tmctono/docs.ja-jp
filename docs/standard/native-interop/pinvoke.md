---
title: プラットフォーム呼び出し (P/Invoke)
description: .NET で P/Invoke を介してネイティブ関数を呼び出す方法について説明します。
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 1a5f2f9d13429f84d5b5bb58d36f015004fb746b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517864"
---
# <a name="platform-invoke-pinvoke"></a><span data-ttu-id="b216f-103">プラットフォーム呼び出し (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="b216f-103">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="b216f-104">P/Invoke は、アンマネージド ライブラリ内の構造体、コールバック、および関数をマネージド コードからアクセスできるようにするテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="b216f-104">P/Invoke is a technology that allows you to access structs, callbacks, and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="b216f-105">P/Invoke API のほとんどは、`System` と `System.Runtime.InteropServices` の 2 つの名前空間に含まれます。</span><span class="sxs-lookup"><span data-stu-id="b216f-105">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="b216f-106">これら 2 つの名前空間を使用すると、ネイティブ コンポーネントと通信する方法を記述するツールを利用できます。</span><span class="sxs-lookup"><span data-stu-id="b216f-106">Using these two namespaces give you the tools to describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="b216f-107">最も一般的な例から始めましょう。これはマネージド コードでアンマネージド 関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b216f-107">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="b216f-108">コマンドライン アプリケーションからメッセージ ボックスを表示してみましょう。</span><span class="sxs-lookup"><span data-stu-id="b216f-108">Let’s show a message box from a command-line application:</span></span>

```csharp
using System.Runtime.InteropServices;

public class Program {

    // Import user32.dll (containing the function we need) and define
    // the method corresponding to the native function.
    [DllImport("user32.dll", CharSet = CharSet.Unicode, SetLastError = true)]
    public static extern int MessageBox(IntPtr hWnd, String text, String caption, int options);

    public static void Main(string[] args) {
        // Invoke the function as a regular managed method.
        MessageBox(IntPtr.Zero, "Command-line message box", "Attention!", 0);
    }
}
```

<span data-ttu-id="b216f-109">上の例は単純ですが、マネージド コードからアンマネージド 関数を呼び出すために必要なことを示しています。</span><span class="sxs-lookup"><span data-stu-id="b216f-109">The previous example is simple, but it does show off what's needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="b216f-110">この例の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="b216f-110">Let’s step through the example:</span></span>

*   <span data-ttu-id="b216f-111">1 行目は、必要なすべての項目を保持する名前空間 `System.Runtime.InteropServices` のステートメントの使用を示しています。</span><span class="sxs-lookup"><span data-stu-id="b216f-111">Line #1 shows the using statement for the `System.Runtime.InteropServices` namespace that holds all the items needed.</span></span>
*   <span data-ttu-id="b216f-112">7 行目で `DllImport` 属性を導入しています。</span><span class="sxs-lookup"><span data-stu-id="b216f-112">Line #7 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="b216f-113">この属性は、ランタイムにアンマネージ DLL を読み込むように伝えるため、きわめて重要です。</span><span class="sxs-lookup"><span data-stu-id="b216f-113">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="b216f-114">渡された文字列は、ターゲット関数が入っている DLL です。</span><span class="sxs-lookup"><span data-stu-id="b216f-114">The string passed in is the DLL our target function is in.</span></span> <span data-ttu-id="b216f-115">さらに、文字列のマーシャリングに使用する[文字セット](./charset.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="b216f-115">Additionally, it specifies which [character set](./charset.md) to use for marshalling the strings.</span></span> <span data-ttu-id="b216f-116">最後に、この関数が [SetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-setlasterror) を呼び出し、ランタイムでそのエラー コードをキャプチャしてユーザーが <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error?displayProperty=nameWithType> を介して取得できるように指定します。</span><span class="sxs-lookup"><span data-stu-id="b216f-116">Finally, it specifies that this function calls [SetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-setlasterror) and that the runtime should capture that error code so the user can retrieve it via <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error?displayProperty=nameWithType>.</span></span>
*   <span data-ttu-id="b216f-117">8 行目は、P/Invoke 作業の最も重要な箇所です。</span><span class="sxs-lookup"><span data-stu-id="b216f-117">Line #8 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="b216f-118">ここでは、アンマネージドと**正確に同じシグネチャ**を持つマネージド メソッドを定義しています。</span><span class="sxs-lookup"><span data-stu-id="b216f-118">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="b216f-119">宣言には新しいキーワード `extern` があることがわかります。これはランタイムに、これが外部メソッドであり、それを呼び出したときに、ランタイムが `DllImport` 属性に指定された DLL からそれを見つける必要があることを伝えます。</span><span class="sxs-lookup"><span data-stu-id="b216f-119">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="b216f-120">例の残りの部分は、その他のマネージド メソッドと同じように、メソッドを呼び出しているだけです。</span><span class="sxs-lookup"><span data-stu-id="b216f-120">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="b216f-121">サンプルは、macOS の場合も似ています。</span><span class="sxs-lookup"><span data-stu-id="b216f-121">The sample is similar for macOS.</span></span> <span data-ttu-id="b216f-122">macOS ではダイナミック ライブラリの名前付けのスキームが異なるため、`DllImport` 属性内のライブラリの名前を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b216f-122">The name of the library in the `DllImport` attribute needs to change since macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="b216f-123">次のサンプルでは、`getpid(2)` 関数を使用して、アプリケーションのプロセス ID を取得し、それをコンソールに出力しています。</span><span class="sxs-lookup"><span data-stu-id="b216f-123">The following sample uses the `getpid(2)` function to get the process ID of the application and print it out to the console:</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libSystem shared library and define the method corresponding to the native function.
        [DllImport("libSystem.dylib")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

<span data-ttu-id="b216f-124">これは Linux でも同様です。</span><span class="sxs-lookup"><span data-stu-id="b216f-124">It is also similar on Linux.</span></span> <span data-ttu-id="b216f-125">`getpid(2)` は標準的な [POSIX](https://en.wikipedia.org/wiki/POSIX) システム コールであるため、関数名が同じです。</span><span class="sxs-lookup"><span data-stu-id="b216f-125">The function name is the same, since `getpid(2)` is a standard [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc shared library and define the method corresponding to the native function.
        [DllImport("libc.so.6")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

## <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="b216f-126">アンマネージド コードからのマネージド コードの呼び出し</span><span class="sxs-lookup"><span data-stu-id="b216f-126">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="b216f-127">ランタイムは通信が双方向にフローする通信を許可しているため、関数ポインターを使用して、ネイティブ関数からマネージド コードをコール バックすることができます。</span><span class="sxs-lookup"><span data-stu-id="b216f-127">The runtime allows communication to flow in both directions, enabling you to call back into managed code from native functions by using function pointers.</span></span> <span data-ttu-id="b216f-128">マネージド コードで、関数ポインターに最も近いものが、**デリゲート**であるため、これをネイティブ コードからマネージド コードへのコールバックを許可するために使います。</span><span class="sxs-lookup"><span data-stu-id="b216f-128">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="b216f-129">この機能を使用する方法は、前述のマネージドからネイティブへのプロセスに似ています。</span><span class="sxs-lookup"><span data-stu-id="b216f-129">The way to use this feature is similar to the managed to native process previously described.</span></span> <span data-ttu-id="b216f-130">指定されたコールバックに対し、ユーザーがシグネチャと一致するデリゲートを定義し、それを外部メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="b216f-130">For a given callback, you define a delegate that matches the signature and pass that into the external method.</span></span> <span data-ttu-id="b216f-131">ランタイムは、他のすべてのことを処理します。</span><span class="sxs-lookup"><span data-stu-id="b216f-131">The runtime will take care of everything else.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace ConsoleApplication1 {

    class Program {

        // Define a delegate that corresponds to the unmanaged function.
        delegate bool EnumWC(IntPtr hwnd, IntPtr lParam);

        // Import user32.dll (containing the function we need) and define
        // the method corresponding to the native function.
        [DllImport("user32.dll")]
        static extern int EnumWindows(EnumWC lpEnumFunc, IntPtr lParam);

        // Define the implementation of the delegate; here, we simply output the window handle.
        static bool OutputWindow(IntPtr hwnd, IntPtr lParam) {
            Console.WriteLine(hwnd.ToInt64());
            return true;
        }

        static void Main(string[] args) {
            // Invoke the method; note the delegate as a first parameter.
            EnumWindows(OutputWindow, IntPtr.Zero);
        }
    }
}
```

<span data-ttu-id="b216f-132">例の手順に従う前に、使用する必要があるアンマネージ関数のシグネチャについて見直しておくのはよいことです。</span><span class="sxs-lookup"><span data-stu-id="b216f-132">Before walking through the example, it's good to review the signatures of the unmanaged functions you need to work with.</span></span> <span data-ttu-id="b216f-133">すべてのウィンドウを列挙するために呼び出す関数は、次のシグネチャを持ちます。`BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="b216f-133">The function to be called to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="b216f-134">最初のパラメーターでは、コールバックです。</span><span class="sxs-lookup"><span data-stu-id="b216f-134">The first parameter is a callback.</span></span> <span data-ttu-id="b216f-135">上記のコールバックのシグネチャは次のとおりです。`BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="b216f-135">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="b216f-136">次の例を確認してみましょう。</span><span class="sxs-lookup"><span data-stu-id="b216f-136">Now, let’s walk through the example:</span></span>

*   <span data-ttu-id="b216f-137">例の 9 行目では、アンマネージ コードからのコールバックのシグネチャと一致するデリゲートを定義しています。</span><span class="sxs-lookup"><span data-stu-id="b216f-137">Line #9 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="b216f-138">マネージド コードで `IntPtr` を使用して、LPARAM および HWND 型を表す方法に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b216f-138">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="b216f-139">13 行目と 14 行目では、user32.dll ライブラリから `EnumWindows` 関数を導入しています。</span><span class="sxs-lookup"><span data-stu-id="b216f-139">Lines #13 and #14 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="b216f-140">17 - 20 行目は、デリゲートを実装しています。</span><span class="sxs-lookup"><span data-stu-id="b216f-140">Lines #17 - 20 implement the delegate.</span></span> <span data-ttu-id="b216f-141">この簡単な例では、ハンドルだけコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="b216f-141">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="b216f-142">最後に、24 行目で、外部メソッドを呼び出し、デリゲートを渡しています。</span><span class="sxs-lookup"><span data-stu-id="b216f-142">Finally, in line #24, the external method is called and passed in the delegate.</span></span>

<span data-ttu-id="b216f-143">Linux と macOS の例を、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="b216f-143">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="b216f-144">それらの場合、`libc` C ライブラリに見つかる `ftw` 関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="b216f-144">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="b216f-145">この関数は、ディレクトリ階層をスキャンするために使用し、そのパラメーターの 1 つとして、関数へのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b216f-145">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="b216f-146">上記のメソッドのシグネチャは次のとおりです。`int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`</span><span class="sxs-lookup"><span data-stu-id="b216f-146">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

            // Define a delegate that has the same signature as the native function.
            delegate int DirClbk(string fName, StatClass stat, int typeFlag);

            // Import the libc and define the method to represent the native function.
            [DllImport("libc.so.6")]
            static extern int ftw(string dirpath, DirClbk cl, int descriptors);

            // Implement the above DirClbk delegate;
            // this one just prints out the filename that is passed to it.
            static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                    Console.WriteLine(fName);
                    return 0;
            }

            public static void Main(string[] args){
                    // Call the native function.
                    // Note the second parameter which represents the delegate (callback).
                    ftw(".", DisplayEntry, 10);
            }
    }

    // The native callback takes a pointer to a struct. The below class
    // represents that struct in managed code. You can find more information
    // about this in the section on marshalling below.
    [StructLayout(LayoutKind.Sequential)]
    public class StatClass {
            public uint DeviceID;
            public uint InodeNumber;
            public uint Mode;
            public uint HardLinks;
            public uint UserID;
            public uint GroupID;
            public uint SpecialDeviceID;
            public ulong Size;
            public ulong BlockSize;
            public uint Blocks;
            public long TimeLastAccess;
            public long TimeLastModification;
            public long TimeLastStatusChange;
    }
}
```

<span data-ttu-id="b216f-147">macOS の例では、同じ関数を使用していますが、唯一の違いは `DllImport` 属性への引数です。macOS は `libc` を別の場所で保持しているためです。</span><span class="sxs-lookup"><span data-stu-id="b216f-147">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
        public static class Program {

                // Define a delegate that has the same signature as the native function.
                delegate int DirClbk(string fName, StatClass stat, int typeFlag);

                // Import the libc and define the method to represent the native function.
                [DllImport("libSystem.dylib")]
                static extern int ftw(string dirpath, DirClbk cl, int descriptors);

                // Implement the above DirClbk delegate;
                // this one just prints out the filename that is passed to it.
                static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                        Console.WriteLine(fName);
                        return 0;
                }

                public static void Main(string[] args){
                        // Call the native function.
                        // Note the second parameter which represents the delegate (callback).
                        ftw(".", DisplayEntry, 10);
                }
        }

        // The native callback takes a pointer to a struct. The below class
        // represents that struct in managed code.
        [StructLayout(LayoutKind.Sequential)]
        public class StatClass {
                public uint DeviceID;
                public uint InodeNumber;
                public uint Mode;
                public uint HardLinks;
                public uint UserID;
                public uint GroupID;
                public uint SpecialDeviceID;
                public ulong Size;
                public ulong BlockSize;
                public uint Blocks;
                public long TimeLastAccess;
                public long TimeLastModification;
                public long TimeLastStatusChange;
        }
}
```

<span data-ttu-id="b216f-148">前述の例のどちらも、パラメーターに依存し、どちらの場合もパラメーターは、マネージド型として指定されています。</span><span class="sxs-lookup"><span data-stu-id="b216f-148">Both of the previous examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="b216f-149">ランタイムは、"正しいこと" を実行し、これらを他方の側で同等のものに処理します。</span><span class="sxs-lookup"><span data-stu-id="b216f-149">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="b216f-150">型をネイティブ コードにマーシャリングする方法については、「[Type marshalling (型のマーシャリング)](type-marshalling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b216f-150">Learn about how types are marshalled to native code in our page on [Type marshalling](type-marshalling.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="b216f-151">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="b216f-151">More resources</span></span>

*   <span data-ttu-id="b216f-152">[PInvoke.net wiki](https://www.pinvoke.net/) は、一般的な Windows API とそれらを呼び出す方法に関する情報を記載した優れた Wiki です。</span><span class="sxs-lookup"><span data-stu-id="b216f-152">[PInvoke.net wiki](https://www.pinvoke.net/) an excellent Wiki with information on common Windows APIs and how to call them.</span></span>
*   [<span data-ttu-id="b216f-153">MSDN の P/Invoke</span><span class="sxs-lookup"><span data-stu-id="b216f-153">P/Invoke on MSDN</span></span>](/cpp/dotnet/native-and-dotnet-interoperability)
*   [<span data-ttu-id="b216f-154">P/invoke に関する Mono のドキュメント</span><span class="sxs-lookup"><span data-stu-id="b216f-154">Mono documentation on P/Invoke</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/)
