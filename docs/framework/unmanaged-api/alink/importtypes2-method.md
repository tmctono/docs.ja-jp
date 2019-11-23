---
title: ImportTypes2 メソッド
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
ms.openlocfilehash: 8dae903ab76ab83ac0818c4bc4a76e81094bdf65
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445669"
---
# <a name="importtypes2-method"></a><span data-ttu-id="71daa-102">ImportTypes2 メソッド</span><span class="sxs-lookup"><span data-stu-id="71daa-102">ImportTypes2 Method</span></span>
<span data-ttu-id="71daa-103">Initiates the import of types.</span><span class="sxs-lookup"><span data-stu-id="71daa-103">Initiates the import of types.</span></span> <span data-ttu-id="71daa-104">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="71daa-104">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71daa-105">構文</span><span class="sxs-lookup"><span data-stu-id="71daa-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="71daa-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71daa-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="71daa-107">ID of assembly into which to import.</span><span class="sxs-lookup"><span data-stu-id="71daa-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="71daa-108">ID of file to from which to import.</span><span class="sxs-lookup"><span data-stu-id="71daa-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="71daa-109">Zero-based scope from which to import.</span><span class="sxs-lookup"><span data-stu-id="71daa-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="71daa-110">Receives enumerator handle for the types in the given scope.</span><span class="sxs-lookup"><span data-stu-id="71daa-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="71daa-111">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="71daa-111">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="71daa-112">Optionally receives count of types in the specified scope.</span><span class="sxs-lookup"><span data-stu-id="71daa-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71daa-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="71daa-113">Return Value</span></span>  
 <span data-ttu-id="71daa-114">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="71daa-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71daa-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="71daa-115">Requirements</span></span>  
 <span data-ttu-id="71daa-116">Requires alink.h</span><span class="sxs-lookup"><span data-stu-id="71daa-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71daa-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="71daa-117">See also</span></span>

- [<span data-ttu-id="71daa-118">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71daa-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="71daa-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71daa-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="71daa-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="71daa-120">ALink API</span></span>](index.md)
