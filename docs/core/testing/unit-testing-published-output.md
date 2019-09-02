---
title: パブリッシュされた出力を dotnet vstest でテストします
description: dotnet vstest コマンドを使用して、ソース コードではなく、パブリッシュされたライブラリでテストを実行する方法を説明します。
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.custom: seodec18
ms.openlocfilehash: 9ac03053bc762d0176e087545871ca8a145cd41e
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168291"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="e3ddc-103">パブリッシュされた出力を dotnet vstest でテストします</span><span class="sxs-lookup"><span data-stu-id="e3ddc-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="e3ddc-104">`dotnet vstest` コマンドを使用して、パブリッシュ済みの出力に対してテストを行えます。</span><span class="sxs-lookup"><span data-stu-id="e3ddc-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="e3ddc-105">これは xUnit、MSTest、および NUnit の各テストで機能します。</span><span class="sxs-lookup"><span data-stu-id="e3ddc-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="e3ddc-106">次のように、パブリッシュされた出力の一部であった DLL ファイルを見つけて実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="e3ddc-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```console
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="e3ddc-107">`<MyPublishedTests>` はパブリッシュされたテスト プロジェクトの名前です。</span><span class="sxs-lookup"><span data-stu-id="e3ddc-107">Where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example"></a><span data-ttu-id="e3ddc-108">例</span><span class="sxs-lookup"><span data-stu-id="e3ddc-108">Example</span></span>

<span data-ttu-id="e3ddc-109">次のコマンドは、パブリッシュされた DLL でのテストの実行を示しています。</span><span class="sxs-lookup"><span data-stu-id="e3ddc-109">The commands below demonstrate running tests on a published DLL.</span></span>

```console
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="e3ddc-110">メモ:アプリが `netcoreapp` 以外のフレームワークを対象とする場合でも、対象のフレームワークでフレームワーク フラグを付けて渡すことで `dotnet vstest` コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e3ddc-110">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="e3ddc-111">たとえば、`dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"` のようにします。</span><span class="sxs-lookup"><span data-stu-id="e3ddc-111">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="e3ddc-112">Visual Studio 2017 Update 5 では、望ましいフレームワークが自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="e3ddc-112">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3ddc-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3ddc-113">See also</span></span>

- [<span data-ttu-id="e3ddc-114">dotnet テストおよび xUnit を使用した単体テスト</span><span class="sxs-lookup"><span data-stu-id="e3ddc-114">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="e3ddc-115">dotnet テストおよび NUnit を使用した単体テスト</span><span class="sxs-lookup"><span data-stu-id="e3ddc-115">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="e3ddc-116">dotnet テストおよび MSTest を使用した単体テスト</span><span class="sxs-lookup"><span data-stu-id="e3ddc-116">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
