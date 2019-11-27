---
title: SetAssemblyFile メソッド
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 1db4c4ab7e47e223a492e08297ac3cedcb3a27eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445607"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="598f3-102">SetAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="598f3-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="598f3-103">ビルドされるアセンブリの名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="598f3-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="598f3-104">非バインドモジュールの生成時には使用しません。</span><span class="sxs-lookup"><span data-stu-id="598f3-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="598f3-105">構文</span><span class="sxs-lookup"><span data-stu-id="598f3-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="598f3-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="598f3-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="598f3-107">マニフェストファイルの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="598f3-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="598f3-108">[IMetaDataEmit インターフェイス](../metadata/imetadataemit-interface.md)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="598f3-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="598f3-109">[Assemblyflags 列挙型](../metadata/assemblyflags-enumeration.md)で定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="598f3-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="598f3-110">結果として得られるアセンブリの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="598f3-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="598f3-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="598f3-111">Return Value</span></span>  
 <span data-ttu-id="598f3-112">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="598f3-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="598f3-113">要件</span><span class="sxs-lookup"><span data-stu-id="598f3-113">Requirements</span></span>  
 <span data-ttu-id="598f3-114">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="598f3-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="598f3-115">参照</span><span class="sxs-lookup"><span data-stu-id="598f3-115">See also</span></span>

- [<span data-ttu-id="598f3-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="598f3-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="598f3-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="598f3-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="598f3-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="598f3-118">ALink API</span></span>](index.md)
