---
title: SetAssemblyFile2 メソッド
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aba11ccd61b65d2a779b39db8e0e082cf4d4015b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787218"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="97f15-102">SetAssemblyFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="97f15-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="97f15-103">新しいアセンブリのオプションとオプションの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="97f15-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="97f15-104">バインドされていないモジュールを生成する場合は、このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="97f15-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f15-105">構文</span><span class="sxs-lookup"><span data-stu-id="97f15-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="97f15-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="97f15-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="97f15-107">マニフェストファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="97f15-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="97f15-108">このファイルの[IMetaDataEmit2 インターフェイス](../metadata/imetadataemit2-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="97f15-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="97f15-109">[Assemblyflags 列挙体](../metadata/assemblyflags-enumeration.md)によって表されるオプション。</span><span class="sxs-lookup"><span data-stu-id="97f15-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="97f15-110">構築されるアセンブリの一意の ID を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="97f15-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97f15-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="97f15-111">Return Value</span></span>  
 <span data-ttu-id="97f15-112">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="97f15-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97f15-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="97f15-113">Requirements</span></span>  
 <span data-ttu-id="97f15-114">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="97f15-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f15-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="97f15-115">See also</span></span>

- [<span data-ttu-id="97f15-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="97f15-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="97f15-117">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="97f15-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="97f15-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="97f15-118">ALink API</span></span>](index.md)
