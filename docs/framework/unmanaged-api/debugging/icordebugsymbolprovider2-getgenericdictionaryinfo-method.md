---
title: ICorDebugSymbolProvider2::GetGenericDictionaryInfo メソッド
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
ms.openlocfilehash: 02ecaf56e845680472f42c04f3978e54e7a69272
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791504"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a><span data-ttu-id="dee17-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="dee17-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo Method</span></span>

<span data-ttu-id="dee17-103">汎用のディクショナリ マップを取得します。</span><span class="sxs-lookup"><span data-stu-id="dee17-103">Retrieves a generic dictionary map.</span></span>

## <a name="syntax"></a><span data-ttu-id="dee17-104">構文</span><span class="sxs-lookup"><span data-stu-id="dee17-104">Syntax</span></span>

```cpp
HRESULT GetGenericDictionaryInfo(
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="dee17-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dee17-105">Parameters</span></span>

`ppMemoryBuffer`\
<span data-ttu-id="dee17-106">入出力ジェネリックディクショナリマップを格納している、[のオブジェクトの](icordebugmemorybuffer-interface.md)アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="dee17-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object containing the generic dictionary map.</span></span> <span data-ttu-id="dee17-107">詳細については、次の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dee17-107">See the Remarks section for more information.</span></span>

## <a name="remarks"></a><span data-ttu-id="dee17-108">コメント</span><span class="sxs-lookup"><span data-stu-id="dee17-108">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="dee17-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="dee17-109">This method is available with .NET Native only.</span></span>

<span data-ttu-id="dee17-110">このマップは最上位レベルの 2 つのセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="dee17-110">The map consists of two top-level sections:</span></span>

- <span data-ttu-id="dee17-111">このマップに含まれるすべてのディクショナリの相対仮想アドレス (RVA) を格納している[ディレクトリ](#Directory)。</span><span class="sxs-lookup"><span data-stu-id="dee17-111">A [directory](#Directory) containing the relative virtual addresses (RVA) of all dictionaries included in this map.</span></span>

- <span data-ttu-id="dee17-112">オブジェクトのインスタンス化情報を格納するバイト固定[ヒープ](#Heap)。</span><span class="sxs-lookup"><span data-stu-id="dee17-112">A byte-aligned [heap](#Heap) that contains object instantiation information.</span></span> <span data-ttu-id="dee17-113">最後のディレクトリ エントリの直後から開始します。</span><span class="sxs-lookup"><span data-stu-id="dee17-113">It starts immediately after the last directory entry.</span></span>

<a name="Directory"></a>

## <a name="the-directory"></a><span data-ttu-id="dee17-114">ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="dee17-114">The Directory</span></span>

<span data-ttu-id="dee17-115">ディレクトリ内の各エントリは、ヒープ内のオフセットを参照します。つまり、これは、ヒープの開始位置を基準としたオフセットです。</span><span class="sxs-lookup"><span data-stu-id="dee17-115">Each entry in the directory refers to an offset inside the heap; that is, it is an offset that is relative to the start of the heap.</span></span> <span data-ttu-id="dee17-116">個々のエントリの値が一意とは限りません。このため、複数のディクショナリ エントリがヒープ内の同一オフセットを指すことがあります。</span><span class="sxs-lookup"><span data-stu-id="dee17-116">The value of individual entries is not necessarily unique; it is possible for multiple directory entries to point to the same offset in the heap.</span></span>

<span data-ttu-id="dee17-117">汎用のディクショナリ マップのディレクトリ部分の構造は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dee17-117">The directory portion of the generic dictionary map has the following structure:</span></span>

- <span data-ttu-id="dee17-118">最初の 4 バイトには、ディクショナリのエントリ数 (ディクショナリ内の相対仮想アドレスの数) が格納されています。</span><span class="sxs-lookup"><span data-stu-id="dee17-118">The first 4 bytes contains the number of dictionary entries (that is, the number of relative virtual addresses in the dictionary).</span></span> <span data-ttu-id="dee17-119">この値は*N*として参照されます。上位ビットが設定されている場合、エントリは相対仮想アドレスで昇順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="dee17-119">We will refer to this value as *N*. If the high bit is set, the entries are sorted by relative virtual address in ascending order.</span></span>

- <span data-ttu-id="dee17-120">*N*ディレクトリエントリは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dee17-120">The *N* directory entries follow.</span></span> <span data-ttu-id="dee17-121">各エントリは 8 バイトであり、次の 2 つの 4 バイト セグメントからなります。</span><span class="sxs-lookup"><span data-stu-id="dee17-121">Each entry consists of 8 bytes, in two 4-byte segments:</span></span>

  - <span data-ttu-id="dee17-122">バイト 0 ～ 3: RVA (ディクショナリの相対仮想アドレス)。</span><span class="sxs-lookup"><span data-stu-id="dee17-122">Bytes 0-3: RVA; the dictionary's relative virtual address.</span></span>

  - <span data-ttu-id="dee17-123">バイト 4 ～ 7: オフセット (ヒープの開始位置を基準としたオフセット)。</span><span class="sxs-lookup"><span data-stu-id="dee17-123">Bytes 4-7: Offset; an offset relative to the start of the heap.</span></span>

<a name="Heap"></a>

## <a name="the-heap"></a><span data-ttu-id="dee17-124">ヒープ</span><span class="sxs-lookup"><span data-stu-id="dee17-124">The Heap</span></span>

<span data-ttu-id="dee17-125">ヒープのサイズは、ストリーム リーダーにより、ディレクトリ サイズ + 4 の値からストリームの長さを差し引くことで算出されます。</span><span class="sxs-lookup"><span data-stu-id="dee17-125">The heap’s size can be computed by a stream reader by subtracting the length of the stream from the directory size + 4.</span></span> <span data-ttu-id="dee17-126">つまり、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dee17-126">In other words:</span></span>

```csharp
Heap Size = Stream.Length – (Directory Size + 4)
```

<span data-ttu-id="dee17-127">ディレクトリのサイズが `N * 8` であるとします。</span><span class="sxs-lookup"><span data-stu-id="dee17-127">where the directory size is `N * 8`.</span></span>

<span data-ttu-id="dee17-128">ヒープの各インスタンス化情報項目の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dee17-128">The format for each instantiation information item on the heap is:</span></span>

- <span data-ttu-id="dee17-129">このインスタンス化情報項目のバイト単位の長さ。圧縮 ECMA メタデータ形式です。</span><span class="sxs-lookup"><span data-stu-id="dee17-129">The length of this instantiation information item in bytes in compressed ECMA metadata format.</span></span> <span data-ttu-id="dee17-130">値では、この長さ情報が除外されます。</span><span class="sxs-lookup"><span data-stu-id="dee17-130">The value excludes this length information.</span></span>

- <span data-ttu-id="dee17-131">圧縮された ECMA メタデータ形式のジェネリックインスタンス化型 ( *T*) の数。</span><span class="sxs-lookup"><span data-stu-id="dee17-131">The number of generic instantiation types, or *T*, in compressed ECMA metadata format.</span></span>

- <span data-ttu-id="dee17-132">*T*型はそれぞれ ECMA 型シグネチャ形式で表されます。</span><span class="sxs-lookup"><span data-stu-id="dee17-132">*T* types, each represented in ECMA type signature format.</span></span>

<span data-ttu-id="dee17-133">各ヒープ要素の長さを含めることで、ヒープに影響を与えずに、ディレクトリ セクションの単純な並べ替えを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dee17-133">The inclusion of the length for each heap element enables simple sorting of the directory section without affecting the heap.</span></span>

## <a name="requirements"></a><span data-ttu-id="dee17-134">要件</span><span class="sxs-lookup"><span data-stu-id="dee17-134">Requirements</span></span>

<span data-ttu-id="dee17-135">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dee17-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="dee17-136">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dee17-136">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="dee17-137">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dee17-137">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="dee17-138">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dee17-138">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="dee17-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="dee17-139">See also</span></span>

- [<span data-ttu-id="dee17-140">ICorDebugSymbolProvider2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dee17-140">ICorDebugSymbolProvider2 Interface</span></span>](icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="dee17-141">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dee17-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
