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
ms.openlocfilehash: 4f710ef9741869a2b4fd8473ed3ecf379cfcc56d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445591"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="7f283-102">SetAssemblyFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="7f283-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="7f283-103">新しいアセンブリのオプションとオプションの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="7f283-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="7f283-104">バインドされていないモジュールを生成する場合は、このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="7f283-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f283-105">構文</span><span class="sxs-lookup"><span data-stu-id="7f283-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f283-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7f283-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="7f283-107">マニフェストファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="7f283-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="7f283-108">このファイルの[IMetaDataEmit2 インターフェイス](../metadata/imetadataemit2-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7f283-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="7f283-109">[Assemblyflags 列挙体](../metadata/assemblyflags-enumeration.md)によって表されるオプション。</span><span class="sxs-lookup"><span data-stu-id="7f283-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="7f283-110">構築されるアセンブリの一意の ID を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7f283-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f283-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="7f283-111">Return Value</span></span>  
 <span data-ttu-id="7f283-112">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="7f283-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f283-113">要件</span><span class="sxs-lookup"><span data-stu-id="7f283-113">Requirements</span></span>  
 <span data-ttu-id="7f283-114">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="7f283-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f283-115">参照</span><span class="sxs-lookup"><span data-stu-id="7f283-115">See also</span></span>

- [<span data-ttu-id="7f283-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f283-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7f283-117">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f283-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7f283-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="7f283-118">ALink API</span></span>](index.md)
