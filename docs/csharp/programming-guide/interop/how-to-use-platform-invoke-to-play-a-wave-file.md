---
title: '方法: プラットフォーム呼び出しを使用して Wave ファイルを再生する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: cf8415b2d501ae2394fa76170eb232da33c3e308
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589101"
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a><span data-ttu-id="55c71-102">方法: プラットフォーム呼び出しを使用して Wave ファイルを再生する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="55c71-102">How to: Use Platform Invoke to Play a Wave File (C# Programming Guide)</span></span>
<span data-ttu-id="55c71-103">以下の C# コードの例では、プラットフォーム呼び出しサービスを使用して、Windows オペレーティング システム上の .wav サウンド ファイルを再生する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="55c71-103">The following C# code example illustrates how to use platform invoke services to play a wave sound file on the Windows operating system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55c71-104">例</span><span class="sxs-lookup"><span data-stu-id="55c71-104">Example</span></span>  
 <span data-ttu-id="55c71-105">このコード例では、`DllImport` を使って `winmm.dll` の `PlaySound` メソッドのエントリ ポイントを `Form1 PlaySound()` としてインポートしています。</span><span class="sxs-lookup"><span data-stu-id="55c71-105">This example code uses `DllImport` to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="55c71-106">この例には、ボタンを含む簡単な Windows フォームがあります。</span><span class="sxs-lookup"><span data-stu-id="55c71-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="55c71-107">ボタンをクリックすると、Windows 標準の <xref:System.Windows.Forms.OpenFileDialog> ダイアログ ボックスが開き、再生するファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="55c71-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="55c71-108">Wave ファイルを選ぶと、そのファイルが `winmm.dll` ライブラリの `PlaySound()` メソッドによって再生されます。</span><span class="sxs-lookup"><span data-stu-id="55c71-108">When a wave file is selected, it is played by using the `PlaySound()` method of the `winmm.dll` library.</span></span> <span data-ttu-id="55c71-109">このメソッドの詳細については、「[Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files)」(Waveform-Audio ファイルで PlaySound 関数を使用する) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55c71-109">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="55c71-110">.wav 拡張子を持つファイルを参照して選び、 **[開く]** をクリックすることで、プラットフォーム呼び出しを使って Wave ファイルを再生します。</span><span class="sxs-lookup"><span data-stu-id="55c71-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="55c71-111">テキスト ボックスに、選んだファイルの完全なパスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55c71-111">A text box shows the full path of the file selected.</span></span>  
  
 <span data-ttu-id="55c71-112">**[ファイルを開く]** ダイアログ ボックスは、次のフィルター設定によって拡張子 .wav を持つファイルのみを表示するようにフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="55c71-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>  
  
 [!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]  
  
 [!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55c71-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="55c71-113">Compiling the Code</span></span>  
  
1. <span data-ttu-id="55c71-114">Visual Studio で新しい C# Windows アプリケーション プロジェクトを作成し、**WinSound** という名前にします。</span><span class="sxs-lookup"><span data-stu-id="55c71-114">Create a new C# Windows Application project in Visual Studio and name it **WinSound**.</span></span>  
  
2. <span data-ttu-id="55c71-115">上記のコードをコピーし、`Form1.cs` ファイルに貼り付けて内容を上書きします。</span><span class="sxs-lookup"><span data-stu-id="55c71-115">Copy the code above, and paste it over the contents of the `Form1.cs` file.</span></span>  
  
3. <span data-ttu-id="55c71-116">次のコードをコピーし、`Form1.Designer.cs` ファイルのすべての既存コードの後の `InitializeComponent()` メソッドに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="55c71-116">Copy the following code, and paste it in the `Form1.Designer.cs` file, in the `InitializeComponent()` method, after any existing code.</span></span>  
  
     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]  
  
4. <span data-ttu-id="55c71-117">コードをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="55c71-117">Compile and run the code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c71-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="55c71-118">See also</span></span>

- [<span data-ttu-id="55c71-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="55c71-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="55c71-120">相互運用性の概要</span><span class="sxs-lookup"><span data-stu-id="55c71-120">Interoperability Overview</span></span>](./interoperability-overview.md)
- [<span data-ttu-id="55c71-121">プラットフォーム呼び出しの詳細</span><span class="sxs-lookup"><span data-stu-id="55c71-121">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="55c71-122">プラットフォーム呼び出しによるデータのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="55c71-122">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
