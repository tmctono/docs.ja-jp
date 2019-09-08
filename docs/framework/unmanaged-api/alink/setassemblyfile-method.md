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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76d341aca7c96e5932a1fc155ccaee17ce6585da
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777004"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="48f1b-102">SetAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="48f1b-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="48f1b-103">ビルドされるアセンブリの名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="48f1b-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="48f1b-104">非バインドモジュールの生成時には使用しません。</span><span class="sxs-lookup"><span data-stu-id="48f1b-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48f1b-105">構文</span><span class="sxs-lookup"><span data-stu-id="48f1b-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="48f1b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48f1b-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="48f1b-107">マニフェストファイルの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="48f1b-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="48f1b-108">[IMetaDataEmit インターフェイス](../metadata/imetadataemit-interface.md)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="48f1b-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="48f1b-109">[Assemblyflags 列挙型](../metadata/assemblyflags-enumeration.md)で定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="48f1b-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="48f1b-110">結果として得られるアセンブリの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="48f1b-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48f1b-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="48f1b-111">Return Value</span></span>  
 <span data-ttu-id="48f1b-112">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="48f1b-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48f1b-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="48f1b-113">Requirements</span></span>  
 <span data-ttu-id="48f1b-114">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="48f1b-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f1b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="48f1b-115">See also</span></span>

- [<span data-ttu-id="48f1b-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48f1b-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="48f1b-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48f1b-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="48f1b-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="48f1b-118">ALink API</span></span>](index.md)
