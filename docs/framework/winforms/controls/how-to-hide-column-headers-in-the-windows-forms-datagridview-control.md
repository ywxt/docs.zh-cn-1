---
title: 如何：隐藏 Windows 窗体 DataGridView 控件中的列标题
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: ff9c32725384219e4ffc98f3a76fcff9f6cfc221
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532270"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a>如何：隐藏 Windows 窗体 DataGridView 控件中的列标题
有时你将想要显示<xref:System.Windows.Forms.DataGridView>无列标题。 在<xref:System.Windows.Forms.DataGridView>控件，<xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A>属性值确定是否显示列标题。  
  
### <a name="to-hide-the-column-headers"></a>若要隐藏列标题  
  
-   将 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> 属性设置为 `false`。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
-   对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>  
 [Windows 窗体 DataGridView 控件中的列、行和单元格基本功能](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
