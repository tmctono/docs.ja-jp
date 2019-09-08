---
title: ExportNestedTypeForwarder メソッド
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb8112d6d2b5c2cbb257db2f20ff4be5a84e827b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787469"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="e8fb7-102">ExportNestedTypeForwarder メソッド</span><span class="sxs-lookup"><span data-stu-id="e8fb7-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="e8fb7-103">入れ子になった型の型フォワーダーを、指定されたアセンブリの型テーブルに追加します。</span><span class="sxs-lookup"><span data-stu-id="e8fb7-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8fb7-104">構文</span><span class="sxs-lookup"><span data-stu-id="e8fb7-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8fb7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8fb7-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e8fb7-106">エクスポート元のアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="e8fb7-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="e8fb7-107">型を定義するファイルのファイルトークンまたはアセンブリ ID。</span><span class="sxs-lookup"><span data-stu-id="e8fb7-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="e8fb7-108">型のトークン。</span><span class="sxs-lookup"><span data-stu-id="e8fb7-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="e8fb7-109">親の種類のトークン。</span><span class="sxs-lookup"><span data-stu-id="e8fb7-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="e8fb7-110">エクスポートする完全修飾型名。</span><span class="sxs-lookup"><span data-stu-id="e8fb7-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e8fb7-111">`ComType``tdPublic` や`tdNested`などのフラグ。</span><span class="sxs-lookup"><span data-stu-id="e8fb7-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="e8fb7-112">エクスポートの種類のトークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e8fb7-112">Receives token of export type.</span></span> <span data-ttu-id="e8fb7-113">これは、入れ子にされた型を出力する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="e8fb7-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8fb7-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="e8fb7-114">Return Value</span></span>  
 <span data-ttu-id="e8fb7-115">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="e8fb7-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8fb7-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="e8fb7-116">Requirements</span></span>  
 <span data-ttu-id="e8fb7-117">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="e8fb7-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8fb7-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8fb7-118">See also</span></span>

- [<span data-ttu-id="e8fb7-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e8fb7-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e8fb7-120">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e8fb7-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e8fb7-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="e8fb7-121">ALink API</span></span>](index.md)
