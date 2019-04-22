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
ms.openlocfilehash: a19762cbec91871d7af617957896e4ee34944fba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132714"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="0d393-102">SetAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="0d393-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="0d393-103">ビルドするアセンブリの名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d393-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="0d393-104">非バインド モジュールを生成するときに使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="0d393-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d393-105">構文</span><span class="sxs-lookup"><span data-stu-id="0d393-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d393-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d393-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="0d393-107">マニフェスト ファイルの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="0d393-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="0d393-108">ポインター [IMetaDataEmit インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="0d393-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="0d393-109">定義されているフラグ[AssemblyFlags 列挙体](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="0d393-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="0d393-110">結果として得られるアセンブリの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0d393-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d393-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="0d393-111">Return Value</span></span>  
 <span data-ttu-id="0d393-112">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="0d393-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d393-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="0d393-113">Requirements</span></span>  
 <span data-ttu-id="0d393-114">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="0d393-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d393-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d393-115">See also</span></span>

- [<span data-ttu-id="0d393-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d393-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="0d393-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d393-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="0d393-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="0d393-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
